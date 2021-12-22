# Java 中的死锁和饥饿

> 原文:[https://www.geeksforgeeks.org/deadlock-starvation-java/](https://www.geeksforgeeks.org/deadlock-starvation-java/)

[**死锁**](https://www.geeksforgeeks.org/operating-system-process-management-deadlock-introduction/) :死锁是两个线程相互等待，等待永不结束的情况。这里两个线程都不能完成它们的任务。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate Deadlock situation
class DeadlockDemo extends Thread {
    static Thread mainThread;
    public void run()
    {
        System.out.println("Child Thread waiting for" +
                          " main thread completion");
        try {

            // Child thread waiting for completion
            // of main thread
            mainThread.join();
        }
        catch (InterruptedException e) {
            System.out.println("Child thread execution" +
                                           " completes");
        }
    }
    public static void main(String[] args)
                   throws InterruptedException
    {
        DeadlockDemo.mainThread = Thread.currentThread();
        DeadlockDemo thread = new DeadlockDemo();

        thread.start();
        System.out.println("Main thread waiting for " +
                            "Child thread completion");

        // main thread is waiting for the completion
        // of Child thread
        thread.join();

        System.out.println("Main thread execution" +
                                      " completes");
    }
}
```

输出:

```
Main thread waiting for Child thread completion
Child Thread waiting for main thread completion
```

[**饥饿**](https://www.geeksforgeeks.org/starvation-aging-operating-systems/) **:** 在饥饿中，线程也在等待对方。但是这里的等待时间并不是无限的，在一段时间间隔之后，等待线程总是获得执行线程 run()方法所需的资源。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate Starvation concept
class StarvationDemo extends Thread {
    static int threadcount = 1;
    public void run()
    {
        System.out.println(threadcount + "st Child" +
                            " Thread execution starts");
        System.out.println("Child thread execution completes");
        threadcount++;
    }
    public static void main(String[] args)
               throws InterruptedException
    {
        System.out.println("Main thread execution starts");

        // Thread priorities are set in a way that thread5
        // gets least priority.
        StarvationDemo thread1 = new StarvationDemo();
        thread1.setPriority(10);
        StarvationDemo thread2 = new StarvationDemo();
        thread2.setPriority(9);
        StarvationDemo thread3 = new StarvationDemo();
        thread3.setPriority(8);
        StarvationDemo thread4 = new StarvationDemo();
        thread4.setPriority(7);
        StarvationDemo thread5 = new StarvationDemo();
        thread5.setPriority(6);

        thread1.start();
        thread2.start();
        thread3.start();
        thread4.start();

        // Here thread5 have to wait because of the
        // other thread. But after waiting for some
        // interval, thread5 will get the chance of
        // execution. It is known as Starvation
        thread5.start();

        System.out.println("Main thread execution completes");
    }
}
```

输出:

```
Main thread execution starts
1st Child Thread execution starts
Child thread execution completes
2st Child Thread execution starts
Child thread execution completes
3st Child Thread execution starts
Child thread execution completes
4st Child Thread execution starts
Child thread execution completes
Main thread execution completes
5st Child Thread execution starts
Child thread execution completes
```