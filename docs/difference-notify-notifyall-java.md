# Java 中 notify()和 notifyAll()的区别

> 原文:[https://www . geesforgeks . org/difference-notify all-Java/](https://www.geeksforgeeks.org/difference-notify-notifyall-java/)

notify()和 notifyAll()方法以及 wait()方法用于在线程之间进行通信。通过调用 wait()方法进入等待状态的线程将处于等待状态，直到任何其他线程在同一对象上调用 notify()或 notifyAll()方法。
现在的问题是 notifyAll()和 notifyAll()方法都是用来给等待的线程进行通知的，那么它们有什么区别或者我们应该在哪里使用 notifyAll()方法，notifyAll()方法应该去哪里？
让我们了解 notify()方法的行为:

```java
// Java program to illustrate the
// behaviour of notify() method
class Geek1 extends Thread {
public void run()
    {
        synchronized(this)
        {
            System.out.println
            (Thread.currentThread().getName() + "...starts");
            try {
                this.wait();
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println
            (Thread.currentThread().getName() + "...notified");
        }
    }
} class Geek2 extends Thread {
    Geek1 geeks1;
    Geek2(Geek1 geeks1)
    {
        this.geeks1 = geeks1;
    }
public void run()
    {
        synchronized(this.geeks1)
        {
            System.out.println
            (Thread.currentThread().getName() + "...starts");

            try {
                this.geeks1.wait();
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println
            (Thread.currentThread().getName() + "...notified");
        }
    }
} class Geek3 extends Thread {
    Geek1 geeks1;
    Geek3(Geek1 geeks1)
    {
        this.geeks1 = geeks1;
    }
public void run()
    {
        synchronized(this.geeks1)
        {
            System.out.println
            (Thread.currentThread().getName() + "...starts");
            this.geeks1.notify();
            System.out.println
            (Thread.currentThread().getName() + "...notified");
        }
    }
} class MainClass {
public static void main(String[] args) throws InterruptedException
    {

        Geek1 geeks1 = new Geek1();
        Geek2 geeks2 = new Geek2(geeks1);
        Geek3 geeks3 = new Geek3(geeks1);
        Thread t1 = new Thread(geeks1, "Thread-1");
        Thread t2 = new Thread(geeks2, "Thread-2");
        Thread t3 = new Thread(geeks3, "Thread-3");
        t1.start();
        t2.start();
        Thread.sleep(100);
        t3.start();
    }
}
```

输出:

```java
Thread-1...start
Thread-2...starts
Thread-3...starts
Thread-3...notified
Thread-1...notified

```

**让我们了解 notifyAll()方法的行为:**

```java
// Java program to illustrate the
// behavior of notifyAll() method
class Geek1 extends Thread {
public void run()
    {
        synchronized(this)
        {
            System.out.println
            (Thread.currentThread().getName() + "...starts");
            try {
                this.wait();
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println
            (Thread.currentThread().getName() + "...notified");
        }
    }
} class Geek2 extends Thread {
    Geek1 geeks1;
    Geek2(Geek1 geeks1)
    {
        this.geeks1 = geeks1;
    }
public void run()
    {
        synchronized(this.geeks1)
        {
            System.out.println
            (Thread.currentThread().getName() + "...starts");

            try {
                this.geeks1.wait();
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println
            (Thread.currentThread().getName() + "...notified");
        }
    }
} class Geek3 extends Thread {
    Geek1 geeks1;
    Geek3(Geek1 geeks1)
    {
        this.geeks1 = geeks1;
    }
public void run()
    {
        synchronized(this.geeks1)
        {
            System.out.println
            (Thread.currentThread().getName() + "...starts");

            this.geeks1.notifyAll();
            System.out.println
            (Thread.currentThread().getName() + "...notified");
        }
    }
} class MainClass {
public static void main(String[] args) throws InterruptedException
    {

        Geek1 geeks1 = new Geek1();
        Geek2 geeks2 = new Geek2(geeks1);
        Geek3 geeks3 = new Geek3(geeks1);
        Thread t1 = new Thread(geeks1, "Thread-1");
        Thread t2 = new Thread(geeks2, "Thread-2");
        Thread t3 = new Thread(geeks3, "Thread-3");
        t1.start();
        t2.start();
        Thread.sleep(100);
        t3.start();
    }
}
```

输出:

```java
Thread-1...starts
Thread-2...starts
Thread-3...starts
Thread-3...notified
Thread-2...notified
Thread-1...notified

```

**notify()和 notifyAll()** 的区别

1.  **通知线程数:**我们可以使用 notify()方法只为等待特定对象的一个线程发出通知**，而借助 notifyAll()方法，我们可以为特定对象的所有等待线程**发出通知**。**
2.  **通过 JVM 通知一个线程:**如果多个线程在等待通知，并且我们使用 notify()方法，那么只有一个线程获得通知，其余线程必须等待进一步的通知。哪个线程会得到我们无法预料的通知，因为这完全取决于 JVM。但是当我们使用 notifyAll()方法时，多个线程得到了通知，但是线程的执行将一个接一个地执行，因为线程需要锁，并且一个对象只有一个锁可用。
3.  **Interchangeability of threads :** We should go for notify() if all your waiting threads are interchangeable (the order they wake up doesn’t matter). A common example is a thread pool. But we should use notifyAll() for other cases where the waiting threads may have different purposes and should be able to run concurrently. An example is a maintenance operation on a shared resource, where multiple threads are waiting for the operation to complete before accessing the resource.

    **何时使用 notify()方法和 notifyAll()**

    *   在互斥锁的情况下，只有一个等待的线程可以在被通知后做一些有用的事情(在这种情况下获取锁)。在这种情况下，您宁愿使用 notify()。如果实现得当，您也可以在这种情况下使用 notifyAll()，但是您将不必要地唤醒那些无论如何都不能做任何事情的线程。
    *   在某些情况下，一旦等待结束，所有等待的线程都可以采取有用的操作。一个例子是一组等待某个任务完成的线程；任务完成后，所有等待的线程都可以继续工作。在这种情况下，您可以使用 notifyAll()同时唤醒所有等待的线程。

    **notify()和 notifyAll()的应用**

    *   对共享资源的维护操作，其中多个线程在访问资源之前等待操作完成；对于这些，我们应该选择 notifyAll()。
    *   假设我们有一个生产者线程和一个消费者线程。生产者生产的每个“包”都应该由消费者消费。消费者将某物放入队列，然后调用 notify()。
    *   我们希望在漫长的过程结束后收到通知。你需要哔一声和屏幕更新。该进程执行 notifyAll()来通知蜂鸣线程和屏幕更新线程。

    **参考:**[https://stackoverflow . com/questions/37026/Java-notify-vs-notifyall-over-over](https://stackoverflow.com/questions/37026/java-notify-vs-notifyall-all-over-again)

    本文由 [**比沙尔·库马尔·杜贝**](https://auth.geeksforgeeks.org/profile.php?user=Bishal Dubey) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。