# Java 中 CountDownLatch 和 CyclicBarrier 的区别

> 原文:[https://www . geeksforgeeks . org/countdowlatch-and-cyclic barrier-in-Java/](https://www.geeksforgeeks.org/difference-between-countdownlatch-and-cyclicbarrier-in-java/)

尽管 [CountDownLatch](https://www.geeksforgeeks.org/countdownlatch-in-java/) 和 [CyclicBarrier](https://www.geeksforgeeks.org/java-util-concurrent-cyclicbarrier-java/#:~:text=In%20other%20words%2C%20a%20CyclicBarrier,threads%20to%20reach%20the%20barrier.) 都被用作同步帮助，允许至少一个线程等待，但是它们之间确实存在差异。了解 java 中 CountDownLatch 和 CyclicBarrier 之间的这些对比将有助于您选择这些实用程序中的哪一个更好地为您服务，显然这也是一个不错的 Java 查询问题。

**CountDownLatch** 是等待多个线程完成或调用倒计时()的线程。当所有线程都调用了倒计时()时，等待线程继续执行。

**例:**

## 爪哇

```java
// Java Program to demonstrate how
// to use CountDownLatch, Its used
// when a thread needs to wait for other
// threads before starting its work.
import java.util.concurrent.CountDownLatch;

public class CountDownLatchDemo {
    public static void main(String args[])
        throws InterruptedException
    {
        // Let us create task that is going to
        // wait for four threads before it starts
        CountDownLatch latch = new CountDownLatch(4);

        // Let us create four worker
        // threads and start them.
        Worker first = new Worker(1000, latch, "WORKER-1");
        Worker second = new Worker(2000, latch, "WORKER-2");
        Worker third = new Worker(3000, latch, "WORKER-3");
        Worker fourth = new Worker(4000, latch, "WORKER-4");
        first.start();
        second.start();
        third.start();
        fourth.start();

        // The main task waits for four threads
        latch.await();

        // Main thread has started
        System.out.println(Thread.currentThread().getName()
                           + " has finished");
    }
}

// A class to represent threads for which
// the main thread waits.
class Worker extends Thread {
    private int delay;
    private CountDownLatch latch;

    public Worker(int delay, CountDownLatch latch,
                  String name)
    {
        super(name);
        this.delay = delay;
        this.latch = latch;
    }

    @Override public void run()
    {
        try {
            Thread.sleep(delay);
            latch.countDown();
            System.out.println(
                Thread.currentThread().getName()
                + " finished");
        }
        catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```

**输出**

```java
WORKER-1 finished
WORKER-2 finished
WORKER-3 finished
WORKER-4 finished
main has finished

```