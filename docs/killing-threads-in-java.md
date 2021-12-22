# 在 Java 中杀死线程

> 原文:[https://www.geeksforgeeks.org/killing-threads-in-java/](https://www.geeksforgeeks.org/killing-threads-in-java/)

run()方法完成后，线程会自动销毁。但是它可能需要在线程完成其[生命周期](https://www.geeksforgeeks.org/lifecycle-and-states-of-a-thread-in-java/)之前终止/停止线程。以前，方法**暂停()**、**恢复()**和**停止()**用于管理线程的执行。但是 Java 2 不赞成这些方法，因为它们可能导致系统故障。暂停/停止线程的现代方法是使用布尔标志和 Thread.interrupt()方法。

*   **使用布尔标志:**我们可以定义一个布尔变量，用于停止/终止线程，比如“退出”。每当我们想要停止一个线程时,“exit”变量将被设置为 true。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// stopping a thread using boolean flag

class MyThread implements Runnable {

    // to stop the thread
    private boolean exit;

    private String name;
    Thread t;

    MyThread(String threadname)
    {
        name = threadname;
        t = new Thread(this, name);
        System.out.println("New thread: " + t);
        exit = false;
        t.start(); // Starting the thread
    }

    // execution of thread starts from run() method
    public void run()
    {
        int i = 0;
        while (!exit) {
            System.out.println(name + ": " + i);
            i++;
            try {
                Thread.sleep(100);
            }
            catch (InterruptedException e) {
                System.out.println("Caught:" + e);
            }
        }
        System.out.println(name + " Stopped.");
    }

    // for stopping the thread
    public void stop()
    {
        exit = true;
    }
}

// Main class
public class Main {
    public static void main(String args[])
    {
        // creating two objects t1 & t2 of MyThread
        MyThread t1 = new MyThread("First  thread");
        MyThread t2 = new MyThread("Second thread");
        try {
            Thread.sleep(500);
            t1.stop(); // stopping thread t1
            t2.stop(); // stopping thread t2
            Thread.sleep(500);
        }
        catch (InterruptedException e) {
            System.out.println("Caught:" + e);
        }
        System.out.println("Exiting the main Thread");
    }
}
```

**Output:** 

```
New thread: Thread[First  thread, 5, main]
New thread: Thread[Second thread, 5, main]
First  thread: 0
Second thread: 0
First  thread: 1
Second thread: 1
First  thread: 2
Second thread: 2
First  thread: 3
Second thread: 3
First  thread: 4
Second thread: 4
First  thread: 5
Second thread Stopped.
First  thread Stopped.
Exiting the main Thread
```

**注意:**每次输出可能会有变化。
通过使用标志，我们可以随时停止线程，并且可以防止不必要的运行时错误。

*   **使用易变布尔标志:**我们也可以使用[易变](https://www.geeksforgeeks.org/volatile-keyword-in-java/)布尔标志来保证我们的代码线程安全。易失性变量直接存储在主内存中，这样线程就不能在本地缓存它的值。当多个线程正在访问同一个变量，并且一个线程所做的更改可能对其他线程不可见时，可能会出现这种情况。在这种情况下，我们可以使用易变的布尔标志。
    让我们考虑下面使用非易失性布尔标志的代码:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate non-volatile boolean flag

public class Main {

    // static used here
    // because a non-static variable
    // cannot be referenced
    // from a static context

    // exit variable to stop both
    // the main and inside threads
    static boolean exit = false;

    public static void main(String[] args)
    {
        System.out.println("started main thread..");

        // a thread inside main thread
        new Thread() {
            public void run()
            {
                System.out.println("started inside thread..");

                // inside thread caches the value of exit,
                // so changes made to exit are not visible here
                while (!exit) // will run infinitely
                {
                }

                // this will not be printed.
                System.out.println("exiting inside thread..");
            }
        }.start();

        try {
            Thread.sleep(500);
        }
        catch (InterruptedException e) {
            System.out.println("Caught :" + e);
        }

        // so that we can stop the threads
        exit = true;
        System.out.println("exiting main thread..");
    }
}
```