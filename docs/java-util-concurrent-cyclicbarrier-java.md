# Java 中的 Java . util . concurrent . cyclic barrier

> 原文:[https://www . geesforgeks . org/Java-util-concurrent-cyclic barrier-Java/](https://www.geeksforgeeks.org/java-util-concurrent-cyclicbarrier-java/)

CyclicBarrier 用于使线程相互等待。当不同的线程处理一部分计算时，以及当所有线程都完成执行时，需要在父线程中组合结果时，使用它。换句话说，当多个线程执行不同的子任务，并且这些子任务的输出需要被组合以形成最终输出时，使用 CyclicBarrier。执行完成后，线程调用 await()方法，等待其他线程到达屏障。一旦所有线程都到达了，障碍就为线程的继续进行让路。

**循环屏障的工作**

CyclicBarriers 在 java.util.concurrent package 中定义。首先，创建一个 CyclicBarriers 的新实例，指定 barriers 应该等待的线程数。

```java
CyclicBarrier newBarrier = new CyclicBarrier(numberOfThreads);
```

每个线程都进行一些计算，在完成计算后，调用 wait()方法，如图所示:

```java
public void run()
{
    // thread does the computation
    newBarrier.await();
}

```

**循环屏障的工作:**

![](img/30c9c648b258abc23029c57a92abece6.png)
一旦调用 await()的线程数等于**的线程数**，屏障就会为等待的线程让路。CyclicBarrier 也可以通过一些操作来初始化，一旦所有线程都到达了该屏障，就会执行这些操作。这个动作可以组合/利用在屏障中等待的单个线程的计算结果。

```java
Runnable action = ... 
//action to be performed when all threads reach the barrier;
CyclicBarrier newBarrier = new CyclicBarrier(numberOfThreads, action);
```

**循环屏障的重要方法:**

1.  **getParties:** Returns the number of parties required to trip this barrier.
    **Syntax:**

    ```java
    public int getParties()
    ```

    **返回:**
    需要多少方才能通过这道屏障

2.  **reset:** Resets the barrier to its initial state.
    **Syntax:**

    ```java
    public void reset()
    ```

    **返回:**
    无效，但将屏障重置为初始状态。如果目前有任何一方在栅栏处等待，他们将带着一个破碎的恐惧返回。

3.  **isBroken:** Queries if this barrier is in a broken state.
    **Syntax:**

    ```java
    public boolean isBroken()
    ```

    **返回:**
    如果一方或多方由于施工或上次重置后的中断或超时，或由于异常导致屏障动作失败，则返回 true 否则为假。

4.  **getNumberWaiting:** Returns the number of parties currently waiting at the barrier.
    **Syntax:**

    ```java
    public int getNumberWaiting()
    ```

    **返回:**
    当前在等待中被阻止的方数()

5.  **等待:**等待，直到各方在此屏障上调用了等待。
    **语法:**

```java
public int await() throws InterruptedException, BrokenBarrierException
```

**返回:**
当前线程的到达索引，其中索引 getParties()–1 表示第一个到达，零表示最后一个到达。

10.  **await:** Waits until all parties have invoked await on this barrier, or the specified waiting time elapses.
    **Syntax:**

    ```java
    public int await(long timeout, TimeUnit unit) 
    throws InterruptedException,
    BrokenBarrierException, TimeoutException
    ```

    **返回:**
    当前线程的到达索引，其中索引 getParties()–1 表示第一个到达，零表示最后一个到达

```java
//JAVA program to demonstrate execution on Cyclic Barrier

import java.util.concurrent.TimeUnit;
import java.util.concurrent.TimeoutException;
import java.util.concurrent.BrokenBarrierException;
import java.util.concurrent.CyclicBarrier;

class Computation1 implements Runnable
{
    public static int product = 0;
    public void run()
    {
        product = 2 * 3;
        try
        {
            Tester.newBarrier.await();
        } 
        catch (InterruptedException | BrokenBarrierException e) 
        {
            e.printStackTrace();
        }
    }
}

class Computation2 implements Runnable
{
    public static int sum = 0;
    public void run()
    {
        // check if newBarrier is broken or not
        System.out.println("Is the barrier broken? - " + Tester.newBarrier.isBroken());
        sum = 10 + 20;
        try
        {
            Tester.newBarrier.await(3000, TimeUnit.MILLISECONDS);

            // number of parties waiting at the barrier
            System.out.println("Number of parties waiting at the barrier "+
            "at this point = " + Tester.newBarrier.getNumberWaiting());
        } 
        catch (InterruptedException | BrokenBarrierException e) 
        {
            e.printStackTrace();
        } 
        catch (TimeoutException e) 
        {
            e.printStackTrace();
        }
    }
}

public class Tester implements Runnable
{
    public static CyclicBarrier newBarrier = new CyclicBarrier(3);

    public static void main(String[] args)
    {
        // parent thread
        Tester test = new Tester();

        Thread t1 = new Thread(test);
        t1.start();
    }
    public void run()
    {
        System.out.println("Number of parties required to trip the barrier = "+
        newBarrier.getParties());
        System.out.println("Sum of product and sum = " + (Computation1.product + 
        Computation2.sum));

        // objects on which the child thread has to run
        Computation1 comp1 = new Computation1();
        Computation2 comp2 = new Computation2();

        // creation of child thread
        Thread t1 = new Thread(comp1);
        Thread t2 = new Thread(comp2);

        // moving child thread to runnable state
        t1.start();
        t2.start();

        try
        {
            Tester.newBarrier.await();
        } 
        catch (InterruptedException | BrokenBarrierException e) 
        {
            e.printStackTrace();
        }

        // barrier breaks as the number of thread waiting for the barrier
        // at this point = 3
        System.out.println("Sum of product and sum = " + (Computation1.product + 
        Computation2.sum));

        // Resetting the newBarrier
        newBarrier.reset();
        System.out.println("Barrier reset successful");
    }
}
```

**输出:**

```java
<Number of parties required to trip the barrier = 3
Sum of product and sum = 0
Is the barrier broken? - false
Number of parties waiting at the barrier at this point = 0
Sum of product and sum = 36
Barrier reset successful
```

**说明:**因为子线程还没有运行设置 sum 和 product 变量的值，所以(sum + product) = 0 的值打印在控制台上。接下来，控制台上会打印(sum + product) = 36，因为子线程运行时设置了 sum 和 product 的值。此外，屏障上的等待线程数达到 3，因此屏障允许所有线程通过，最终打印出 36 个。“此时在屏障处等待的参与方数量”的值= 0，因为所有三个线程都已经调用了 await()方法，因此屏障不再活动。最后，newBarrier 被重置，可以再次使用。

经纪例外

当任何等待的线程离开屏障时，屏障就会被破坏。当一个或多个等待线程被中断或等待时间结束时，会发生这种情况，因为线程调用了 await()方法，超时如下:

```java
newBarrier.await(1000, TimeUnit.MILLISECONDS);
// thread calling this await() 
// methods waits for only 1000 milliseconds.
```

当屏障由于一个或多个参与线程而被打破时，所有其他线程的 await()方法都会抛出一个 BrokenThreadException。而已经在屏障中等待的线程的 await()调用被终止。

**循环障碍和计数障碍的区别**

*   CountDownLatch 在程序中只能使用一次(直到它的计数达到 0)。
*   一旦屏障中的所有线程被释放，就可以一次又一次地使用循环屏障。

**参考:** [甲骨文](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/CyclicBarrier.html)

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。