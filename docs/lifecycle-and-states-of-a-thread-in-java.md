# Java 中线程的生命周期和状态

> 原文:[https://www . geesforgeks . org/生命周期和 java 线程状态/](https://www.geeksforgeeks.org/lifecycle-and-states-of-a-thread-in-java/)

Java 中任意时间点的[线程](https://www.geeksforgeeks.org/multithreading-in-java/)存在于以下任意一种状态。线程在任何时刻都只处于所示状态之一:

1.  新的
2.  可追捕的
3.  堵塞的
4.  等待
5.  定时等待
6.  终止的

下图显示了线程在任何时刻的各种状态。

[![](img/08fcd1e73677af23c3764ffe2db2d888.png)](https:contribute.geeksforgeeks.org/wp-content/uploads/threadLifeCycle.jpg) 
**图片来源:** [Core Java Vol 1，第 9 版，霍斯特曼，Cay S. & Cornell，Gary_2013](https://www.google.co.in/search?q=Core+Java+Vol+1%2C+9th+Edition%2C+Horstmann%2C+Cay+S.+%26+Cornell%2C+Gary_2013&oq=Core+Java+Vol+1%2C+9th+Edition%2C+Horstmann%2C+Cay+S.+%26+Cornell%2C+Gary_2013&aqs=chrome..69i57.383j0j7&sourceid=chrome&ie=UTF-8)

**线程的生命周期**

1.  **新线程:**新线程创建后，处于新状态。当线程处于此状态时，线程尚未开始运行。当一个线程处于新状态时，它的代码还没有运行，还没有开始执行。
2.  **可运行状态:**准备运行的线程被移动到可运行状态。在这种状态下，线程可能实际上正在运行，也可能随时准备运行。线程调度器的责任是给线程运行的时间。
    多线程程序为每个线程分配固定的时间。每个线程都运行一小段时间，然后暂停，将 CPU 让给另一个线程，这样其他线程就有机会运行。当这种情况发生时，所有准备运行的线程都处于可运行状态，等待中央处理器和当前运行的线程。
3.  **Blocked/Waiting state:**When a thread is temporarily inactive, then it’s in one of the following states:
    *   堵塞的
    *   等待

    例如，当一个线程正在等待输入/输出完成时，它就处于阻塞状态。线程调度器负责重新激活和调度阻塞/等待的线程。处于这种状态的线程在进入可运行状态之前不能继续执行。处于这些状态的任何线程都不会消耗任何 CPU 周期。

    当一个线程试图访问当前被其他线程锁定的受保护代码段时，它就处于阻塞状态。当受保护的部分被解锁时，调度为该部分挑选一个被阻塞的线程，并将其移动到可运行状态。然而，当一个线程在某个条件下等待另一个线程时，它就处于等待状态。当这个条件满足时，调度器被通知，等待的线程被移动到可运行状态。

    如果当前正在运行的线程被移动到阻塞/等待状态，则线程调度器会调度另一个处于可运行状态的线程运行。线程调度器负责确定运行哪个线程。

4.  **定时等待:**线程调用带超时参数的方法时，处于定时等待状态。线程处于这种状态，直到超时完成或收到通知。例如，当一个线程调用睡眠或条件等待时，它会被移动到定时等待状态。
5.  **Terminated State:** A thread terminates because of either of the following reasons:
    *   因为它正常存在。当线程的代码完全由程序执行时，就会发生这种情况。
    *   因为出现了一些不寻常的错误事件，如分段错误或未处理的异常。

    处于终止状态的线程不再消耗任何 CPU 周期。

**在 Java 中实现线程状态**

在 Java 中，要获取线程的当前状态，使用 **Thread.getState()** 方法获取线程的当前状态。Java 提供了 **java.lang.Thread.State** 类，该类为线程的状态定义了 ENUM 常量，其概要如下:

1.  **Constant type:** New

    ```
    Declaration: public static final Thread.State NEW
    ```

    **描述:**尚未启动的线程的线程状态。

2.  **Constant type:** Runnable

    ```
    Declaration: public static final Thread.State RUNNABLE
    ```

    **描述:**可运行线程的线程状态。处于可运行状态的线程正在 Java 虚拟机中执行，但它可能正在等待操作系统的其他资源，如处理器。

3.  **Constant type:** Blocked

    ```
    Declaration: public static final Thread.State BLOCKED
    ```

    **描述:**等待监视器锁定的线程被阻塞的线程状态。处于阻塞状态的线程正在等待监视器锁进入同步块/方法，或者在调用 Object.wait()后重新进入同步块/方法。

4.  **常量类型:**等待

```
Declaration: public static final Thread.State WAITING
```

**描述:**等待线程的线程状态。等待线程的线程状态。由于调用以下方法之一，线程处于等待状态:

*   对象。不超时等待
*   [线程连接](https://www.geeksforgeeks.org/joining-threads-in-java/)没有超时
*   LockSupport.park

处于等待状态的线程正在等待另一个线程执行特定的操作。

*   **Constant type:** Timed Waiting

    ```
    Declaration: public static final Thread.State TIMED_WAITING
    ```

    **描述:**等待时间指定的等待线程的线程状态。由于以指定的正等待时间调用以下方法之一，线程处于定时等待状态:

    *   线程。睡眠
    *   对象。超时等待
    *   Thread.join 超时
    *   LockSupport.parkNanos
    *   锁定支持.停车直到*   **Constant type:** Terminated

    ```
    Declaration: public static final Thread.State TERMINATED
    ```

    **描述:**终止线程的线程状态。线程已完成执行。

```
// Java program to demonstrate thread states
class thread implements Runnable
{
    public void run()
    {
        // moving thread2 to timed waiting state
        try
        {
            Thread.sleep(1500);
        } 
        catch (InterruptedException e) 
        {
            e.printStackTrace();
        }

        System.out.println("State of thread1 while it called join() method on thread2 -"+
            Test.thread1.getState());
        try
        {
            Thread.sleep(200);
        } 
        catch (InterruptedException e) 
        {
            e.printStackTrace();
        }     
    }
}

public class Test implements Runnable
{
    public static Thread thread1;
    public static Test obj;

    public static void main(String[] args)
    {
        obj = new Test();
        thread1 = new Thread(obj);

        // thread1 created and is currently in the NEW state.
        System.out.println("State of thread1 after creating it - " + thread1.getState());
        thread1.start();

        // thread1 moved to Runnable state
        System.out.println("State of thread1 after calling .start() method on it - " + 
            thread1.getState());
    }

    public void run()
    {
        thread myThread = new thread();
        Thread thread2 = new Thread(myThread);

        // thread1 created and is currently in the NEW state.
        System.out.println("State of thread2 after creating it - "+ thread2.getState());
        thread2.start();

        // thread2 moved to Runnable state
        System.out.println("State of thread2 after calling .start() method on it - " + 
            thread2.getState());

        // moving thread1 to timed waiting state
        try
        {
            //moving thread1 to timed waiting state
            Thread.sleep(200);
        } 
        catch (InterruptedException e) 
        {
            e.printStackTrace();
        }
        System.out.println("State of thread2 after calling .sleep() method on it - "+ 
            thread2.getState() );

        try 
        {
            // waiting for thread2 to die
            thread2.join();
        } 
        catch (InterruptedException e) 
        {
            e.printStackTrace();
        }
        System.out.println("State of thread2 when it has finished it's execution - " + 
            thread2.getState());
    }

}
```

**输出:**

```
State of thread1 after creating it - NEW
State of thread1 after calling .start() method on it - RUNNABLE
State of thread2 after creating it - NEW
State of thread2 after calling .start() method on it - RUNNABLE
State of thread2 after calling .sleep() method on it - TIMED_WAITING
State of thread1 while it called join() method on thread2 -WAITING
State of thread2 when it has finished it's execution - TERMINATED

```

**说明:**创建新线程时，线程处于 new 状态。什么时候？在线程上调用 start()方法，线程调度器将其移动到 Runnable 状态。每当在线程实例上调用 join()方法时，执行该语句的当前线程将等待该线程进入终止状态。因此，在控制台上打印最终语句之前，程序调用 thread2 上的 join()使 thread1 等待 thread2 完成其执行并移动到 Terminated 状态。线程 1 进入等待状态，因为它正在等待线程 2 完成它的执行，因为它已经在线程 2 上调用了 join。

**所用参考文献:** [甲骨文](https://docs.oracle.com/javase/8/docs/api/java/lang/Thread.State.html)、[核心 Java 第 1 卷第 9 版，霍斯特曼，Cay S. &康乃尔，Gary_2013](https://www.google.co.in/search?q=Core+Java+Vol+1%2C+9th+Edition%2C+Horstmann%2C+Cay+S.+%26+Cornell%2C+Gary_2013&oq=Core+Java+Vol+1%2C+9th+Edition%2C+Horstmann%2C+Cay+S.+%26+Cornell%2C+Gary_2013&aqs=chrome..69i57.383j0j7&sourceid=chrome&ie=UTF-8)

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。