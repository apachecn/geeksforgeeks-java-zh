# Java 中的可调用和未来

> 原文:[https://www.geeksforgeeks.org/callable-future-java/](https://www.geeksforgeeks.org/callable-future-java/)

先决条件:[螺纹](https://www.geeksforgeeks.org/thread-in-operating-system/)、[多线程](https://www.geeksforgeeks.org/multithreading-in-java/)

**可调用的需求**

有两种创建线程的方法——一种是通过扩展线程类，另一种是通过用 Runnable 创建线程。然而，Runnable 中缺少的一个特性是，当线程终止时，即 run()完成时，我们不能使线程返回结果。为了支持这个特性，Java 中提供了可调用接口。

**可调用与可运行**

*   对于实现 Runnable，需要实现 run()方法，该方法不返回任何内容，而对于 Callable，需要实现 call()方法，该方法在完成时返回一个结果。请注意，线程不能用 Callable 创建，只能用 Runnable 创建。
*   另一个区别是 call()方法可以引发异常，而 run()不能。

实现 Callable 必须重写的方法签名。

```java
public Object call() throws Exception;
```

下面是 Callable 示例的代码，它将在大约 0–4 秒的延迟后返回一个随机数。

```java
// Java program to illustrate Callable
// to return a random number
import java.util.Random;
import java.util.concurrent.Callable;
import java.util.concurrent.FutureTask;

class CallableExample implements Callable
{

    public Object call() throws Exception
    {
        // Create random number generator
        Random generator = new Random();

        Integer randomNumber = generator.nextInt(5);

        // To simulate a heavy computation,
        // we delay the thread for some random time
        Thread.sleep(randomNumber * 1000);

        return randomNumber;
    }
}
```

**未来**

当调用()方法完成时，答案必须存储在主线程已知的对象中，这样主线程就可以知道线程返回的结果。程序以后如何存储和获取这个结果？为此，可以使用一个未来对象。把未来想象成一个持有结果的对象——它现在可能不会持有结果，但将来会持有结果(一旦可调用返回)。因此，未来基本上是主线程跟踪其他线程的进度和结果的一种方式。为了实现这个接口，必须重写 5 个方法，但是由于下面的例子使用了库的具体实现，这里只列出了重要的方法。

请注意，可调用和未来做了两件不同的事情——可调用类似于可运行，因为它封装了一个要在另一个线程上运行的任务，而未来用于存储从不同线程获得的结果。事实上，未来也可以与 Runnable 一起工作，这一点将在执行者出现时变得清晰。

*   **公共布尔取消(布尔 mayInterrupt):** 用于停止任务。如果任务尚未开始，它将停止。如果它已经启动，只有当 mayInterrupt 为真时，它才会中断任务。
*   **公共对象 get()抛出中断异常，ExecutionException:** 用于获取任务的结果。如果任务完成，它会立即返回结果，否则它会等到任务完成，然后返回结果。
*   **公共布尔 isDone():** 如果任务完成则返回 true，否则返回 false

要创建线程，需要一个 Runnable。为了获得结果，需要一个未来。

Java 库有具体的类型 FutureTask，它实现了 Runnable 和 Future，方便地结合了这两种功能。
通过为其构造函数提供一个可调用的。然后将 FutureTask 对象提供给 Thread 的构造函数来创建 Thread 对象。因此，间接的，线程是用一个可调用的。为了进一步强调，请注意，没有办法直接用 Callable 创建线程。

下面是使用 Callable 和 FutureTask 的完整示例的代码。

```java
// Java program to illustrate Callable and FutureTask
// for random number generation
import java.util.Random;
import java.util.concurrent.Callable;
import java.util.concurrent.FutureTask;

class CallableExample implements Callable
{

  public Object call() throws Exception
  {
    Random generator = new Random();
    Integer randomNumber = generator.nextInt(5);

    Thread.sleep(randomNumber * 1000);

    return randomNumber;
  }

}

public class CallableFutureTest
{
  public static void main(String[] args) throws Exception
  {

    // FutureTask is a concrete class that
    // implements both Runnable and Future
    FutureTask[] randomNumberTasks = new FutureTask[5];

    for (int i = 0; i < 5; i++)
    {
      Callable callable = new CallableExample();

      // Create the FutureTask with Callable
      randomNumberTasks[i] = new FutureTask(callable);

      // As it implements Runnable, create Thread
      // with FutureTask
      Thread t = new Thread(randomNumberTasks[i]);
      t.start();
    }

    for (int i = 0; i < 5; i++)
    {
      // As it implements Future, we can call get()
      System.out.println(randomNumberTasks[i].get());

      // This method blocks till the result is obtained
      // The get method can throw checked exceptions
      // like when it is interrupted. This is the reason
      // for adding the throws clause to main
    }
  }
}
```

输出:

```java
4
2
3
3
0

```

线程启动后与它的所有交互都是使用 FutureTask 对象，因为它实现了 Future 接口。因此，不需要存储线程对象。使用 FutureTask 对象，可以取消任务，检查任务是否完成，或者尝试获得结果。

下面是只使用 Runnable 的代码。

```java
// Java program to illustrate Runnable
// for random number generation
import java.util.Random;
import java.util.concurrent.Callable;
import java.util.concurrent.FutureTask;

class RunnableExample implements Runnable
{
    // Shared object to store result
    private Object result = null;

    public void run()
    {
        Random generator = new Random();
        Integer randomNumber = generator.nextInt(5);

        // As run cannot throw any Exception
        try
        {
            Thread.sleep(randomNumber * 1000);
        }
        catch (InterruptedException e)
        {
            e.printStackTrace();
        }

        // Store the return value in result when done
        result = randomNumber;

        // Wake up threads blocked on the get() method
        synchronized(this)
        {
            notifyAll();
        }
    }

    public synchronized Object get()
          throws InterruptedException
    {
        while (result == null)
            wait();

        return result;
    }
}

// Code is almost same as the previous example with a
// few changes made to use Runnable instead of Callable
public class RunnableTest
{
    public static void main(String[] args) throws Exception
    {
        RunnableExample[] randomNumberTasks = new RunnableExample[5];

        for (int i = 0; i < 5; i++)
        {
            randomNumberTasks[i] = new RunnableExample();
            Thread t = new Thread(randomNumberTasks[i]);
            t.start();
        }

        for (int i = 0; i < 5; i++)
            System.out.println(randomNumberTasks[i].get());
    }
}
```

**样本输出** 

```java
0
4
3
1
4
2

```

**参考文献**

*   [https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/callable . html](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/Callable.html)
*   [https://docs . Oracle . com/javase/7/docs/API/Java/lang/runnable . html](https://docs.oracle.com/javase/7/docs/api/java/lang/Runnable.html)
*   [https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/futuretask . html](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/FutureTask.html)

本文由**西达尔特·桑达尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。