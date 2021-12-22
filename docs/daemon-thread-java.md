# Java 中的守护线程

> 原文:[https://www.geeksforgeeks.org/daemon-thread-java/](https://www.geeksforgeeks.org/daemon-thread-java/)

Java 中的守护线程是一个低优先级线程，在后台运行，执行垃圾收集等任务。Java 中的守护线程也是一个服务提供者线程，为用户线程提供服务。它的生命依赖于用户线程的支配，即当所有用户线程死亡时，JVM 自动终止这个线程。

简单来说，我们可以说它为用户线程提供后台支持任务的服务。除了服务用户线程，它在生活中没有任何作用。

**Java 中守护线程示例:**Java 中的垃圾收集(gc)、终结器等。

**Java 守护线程的属性**

*   当所有用户线程完成执行时，它们不能阻止 JVM 退出。
*   当所有用户线程完成它们的执行时，JVM 终止自己。
*   如果 JVM 找到一个正在运行的守护线程，它会终止该线程，然后关闭它。JVM 不关心守护线程是否在运行。
*   这是一个极低优先级的线程。

### 守护程序线程的默认性质

默认情况下，主线程始终是非守护进程，但是对于所有剩余的线程，守护进程的性质将从父线程继承到子线程。也就是说，如果父进程是守护进程，那么子进程也是守护进程，如果父进程是非守护进程，那么子进程也是非守护进程。

> **注意:**只要最后一个非守护线程终止，所有守护线程都会自动终止。

### 守护线程的方法

#### 1\. void setDaemon(boolean status):

此方法将当前线程标记为守护线程或用户线程。例如，如果我有一个用户线程 tU，那么 tU.setDaemon(真)将使它成为 Daemon 线程。另一方面，如果我有一个守护线程 tD，那么调用 tD.setDaemon(false)会使它成为一个用户线程。

**语法:**

```
public final void setDaemon(boolean on)
```

**参数:**

*   **On:** If true, mark this thread as a daemon thread.

**异常:**

*   **illegalthreadstateeexception** : If only this thread is active.
*   **SecurityException:** If the current thread cannot modify this thread.

#### 2.boolean isDaemon():

此方法用于检查当前线程是否是守护进程。如果线程是守护进程，则返回真。否则，它返回 false。

**语法:**

```
public final boolean isDaemon()
```

**返回:**

如果此线程是守护程序线程，则此方法返回 true 假不然

## 爪哇

T0T6】

**输出:**

```
t1 is Daemon thread
t3 is Daemon thread
t2 is User thread
```

### 守护程序线程中的异常

如果在启动线程后调用 setDaemon()方法，它会抛出**illegalthreadstatexception**。

## 爪哇

```
// Java program to demonstrate the usage of
// exception in Daemon() Thread

public class DaemonThread extends Thread
{
    public void run()
    {
        System.out.println("Thread name: " + Thread.currentThread().getName());
        System.out.println("Check if its DaemonThread: "
                        + Thread.currentThread().isDaemon());
    }

    public static void main(String[] args)
    {
        DaemonThread t1 = new DaemonThread();
        DaemonThread t2 = new DaemonThread();
        t1.start();

        // Exception as the thread is already started
        t1.setDaemon(true);

        t2.start();
    }
}
```

**运行时异常:**

```
Exception in thread "main" java.lang.IllegalThreadStateException
    at java.lang.Thread.setDaemon(Thread.java:1352)
    at DaemonThread.main(DaemonThread.java:19)
```

**输出:**

```
Thread name: Thread-0
Check if its DaemonThread: false
```

这清楚地表明，我们不能在启动线程后调用 setDaemon()方法。

#### 守护进程与用户线程

1.  **优先级:**当进程中剩下的线程只有守护线程时，解释器退出。这是有意义的，因为当只剩下守护线程时，守护线程就不能为其他线程提供服务了。
2.  **用法:**守护线程是为后台支持任务向用户线程提供服务。

本文由 [**Saket Kumar**](https://www.facebook.com/saketkumar95) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。