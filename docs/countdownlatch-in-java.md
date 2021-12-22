# Java 中的 counttowlatch

> 原文:[https://www.geeksforgeeks.org/countdownlatch-in-java/](https://www.geeksforgeeks.org/countdownlatch-in-java/)

CountDownLatch 用于确保任务在启动前等待其他线程。为了理解它的应用，让我们考虑一个服务器，在这个服务器中，只有当所有需要的服务都启动时，主任务才能启动。

**countdowlatch 的工作:**
当我们创建 countdowlatch 的对象时，我们指定它应该等待的线程数，一旦这些线程完成或准备好工作，就需要通过调用 countdowlatch .倒计时()来进行倒计时。一旦计数达到零，等待任务就开始运行。

**JAVA 中 CountDownLatch 的例子:**

```java
// Java Program to demonstrate how 
// to use CountDownLatch, Its used 
// when a thread needs to wait for other 
// threads before starting its work.
import java.util.concurrent.CountDownLatch;

public class CountDownLatchDemo
{
    public static void main(String args[]) 
                   throws InterruptedException
    {
        // Let us create task that is going to 
        // wait for four threads before it starts
        CountDownLatch latch = new CountDownLatch(4);

        // Let us create four worker 
        // threads and start them.
        Worker first = new Worker(1000, latch, 
                                  "WORKER-1");
        Worker second = new Worker(2000, latch, 
                                  "WORKER-2");
        Worker third = new Worker(3000, latch, 
                                  "WORKER-3");
        Worker fourth = new Worker(4000, latch, 
                                  "WORKER-4");
        first.start();
        second.start();
        third.start();
        fourth.start();

        // The main task waits for four threads
        latch.await();

        // Main thread has started
        System.out.println(Thread.currentThread().getName() +
                           " has finished");
    }
}

// A class to represent threads for which
// the main thread waits.
class Worker extends Thread
{
    private int delay;
    private CountDownLatch latch;

    public Worker(int delay, CountDownLatch latch,
                                    String name)
    {
        super(name);
        this.delay = delay;
        this.latch = latch;
    }

    @Override
    public void run()
    {
        try
        {
            Thread.sleep(delay);
            latch.countDown();
            System.out.println(Thread.currentThread().getName()
                            + " finished");
        }
        catch (InterruptedException e)
        {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
WORKER-1 finished
WORKER-2 finished
WORKER-3 finished
WORKER-4 finished
main has finished

```

**关于计数批次的事实:**

1.  通过将一个 int 传递给一个 CountDownLatch 的构造函数(count)来创建一个 count downlatch 的对象，实际上是一个事件的被邀请方(线程)的数量。
2.  依赖其他线程开始处理的线程会一直等待，直到所有其他线程都调用 count down。一旦递减计数达到零，所有等待 wait()的线程将一起进行。
3.  倒计时()方法递减计数，并等待()方法阻塞，直到计数= 0

本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。