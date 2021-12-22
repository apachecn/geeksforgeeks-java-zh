# Java 中的 JVM 关机钩子

> 原文:[https://www.geeksforgeeks.org/jvm-shutdown-hook-java/](https://www.geeksforgeeks.org/jvm-shutdown-hook-java/)

关闭钩子是一种特殊的构造，允许开发人员在 JVM 关闭时插入一段要执行的代码。这在我们需要进行特殊清理操作以防虚拟机关闭的情况下非常有用。
使用一般的结构来处理这个问题，例如确保我们在应用程序退出之前调用一个特殊的过程(调用 System.exit(0))对于虚拟机由于外部原因(例如。来自操作系统的终止请求)，或者由于资源问题(内存不足)。正如我们将很快看到的，关闭挂钩很容易解决这个问题，它允许我们提供一个任意代码块，当 JVM 关闭时，它会调用这个代码块。
从表面上看，使用关机钩子是非常简单的。我们所要做的就是简单地编写一个扩展 java.lang.Thread 类的类，并在公共 void run()方法中提供我们想要在虚拟机关闭时执行的逻辑。然后我们通过调用 Runtime.getRuntime()将这个类的一个实例注册为虚拟机的关闭钩子。addShutdownHook(线程)方法。如果您需要移除先前注册的关闭钩子，运行时类也提供了 removeShutdownHook(线程)方法。
**示例 1(匿名内部类):**

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class ShutDownHook
{
  public static void main(String[] args)
  {

    Runtime.getRuntime().addShutdownHook(new Thread()
    {
      public void run()
      {
        System.out.println("Shutdown Hook is running !");
      }
    });
    System.out.println("Application Terminating ...");
  }
}
```

当我们运行上面的代码时，您会看到当 JVM 完成主方法的执行时，关机钩子正在被 JVM 调用。
输出:

```
Application Terminating ...
Shutdown Hook is running !
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class ThreadChild extends Thread {

    public void run() {

        System.out.println("In clean up code");
        System.out.println("In shutdown hook");
    }
}

class Demo {

    public static void main(String[] args) {

        Runtime current = Runtime.getRuntime();
        current.addShutdownHook(new ThreadChild());

        for(int i = 1; i <= 10; i++)
            System.out.println("2 X " + i + " = " + 2 * i);
    }
}
```

输出:

```
2 X 1 = 2
2 X 2 = 4
2 X 3 = 6
2 X 4 = 8
2 X 5 = 10
2 X 6 = 12
2 X 7 = 14
2 X 8 = 16
2 X 9 = 18
2 X 10 = 20
In clean up code
In shutdown hook
```

简单对吗？是的，它是。
虽然编写一个关闭钩子非常简单，但是我们需要知道关闭钩子背后的内部，以便正确使用它们。因此，在本文中，我们将探讨关机挂钩设计背后的一些“陷阱”。
**1。在某些情况下可能不会执行关机挂钩！**
首先要记住的是，不能保证关机钩子会一直运行。如果 JVM 由于一些内部错误而崩溃，那么它可能会崩溃而没有机会执行一条指令。此外，如果操作系统发出信号(在 Unix/Linux 中为 kill -9)或终止进程(在 Windows 中为 TerminateProcess)，则应用程序需要立即终止，甚至不需要等待任何清理活动。除此之外，还可以通过调用 Runtime.halt()方法来终止 JVM，而不允许关闭挂钩运行。
当应用程序正常终止时(当所有线程完成时，或者当调用 System.exit(0)时)，调用关闭钩子。此外，当 JVM 由于外部原因而关闭时，例如用户请求终止(Ctrl+C)，由操作系统发出的 SIGTERM(正常终止命令，不带-9)，或者当操作系统关闭时。
**2。一旦启动，关闭挂钩可以在完成前强制停止。**
这其实是之前解释过的案例的特例。虽然钩子开始执行，但是在操作系统关闭等情况下，它可能会在执行完成之前被终止。在这种情况下，一旦给出了 SIGTERM，操作系统就会等待一个进程终止一段指定的时间。如果进程没有在这个时间限制内终止，那么操作系统通过发出一个 SIGTERM(或 Windows 中的对应项)来强制终止进程。因此，当关闭钩子执行到一半时，可能会发生这种情况。
因此，建议确保关机钩子写得谨慎，确保快速完成，不要造成死锁等情况。此外，JavaDoc [1]特别提到，不应该在关闭挂钩中执行长时间的计算或等待用户输入/输出操作。
**3。我们可以有多个关机钩子，但是它们的执行顺序不能保证。**
根据 addShutdownHook 方法(而不是 setShutdownHook)的方法名，您可能已经正确猜到，您可以注册多个关机钩子。但是 JVM 不能保证这些多个钩子的执行顺序。JVM 可以以任意顺序执行关闭钩子。此外，JVM 可能会同时执行所有这些钩子。
**4。我们不能在关机钩子**
中注册/注销关机钩子，一旦 JVM 启动关机序列，就不允许添加或移除任何现有的关机钩子。如果尝试这样做，JVM 将抛出 IllegalStateException。
**5。一旦关闭序列开始，它只能由 Runtime.halt()停止。**
一旦关闭序列开始，只有 Runtime.halt()(强制终止 JVM)可以停止关闭序列的执行(SIGKILL 等外部影响除外)。这意味着在关闭挂钩中调用 System.exit()将不起作用。实际上，如果您在关闭钩子中调用 System.exit()，虚拟机可能会卡住，我们可能不得不强制终止进程。
**6。使用关机挂钩需要安全权限。**
如果我们使用的是 Java Security Managers，那么执行添加/移除关机钩子的代码在运行时需要拥有关机钩子权限。如果我们在安全环境中未经许可调用这个方法，那么它将导致安全异常。
**参考文献:**
[http://docs . Oracle . com/javase/1 . 5 . 0/docs/API/Java/lang/runtime . html # addshutdowhook(Java . lang . thread)](http://docs.oracle.com/javase/1.5.0/docs/api/java/lang/Runtime.html#addShutdownHook(java.lang.Thread))
本文由 [**Saket Kumar**](https://www.facebook.com/saketkumar95) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。