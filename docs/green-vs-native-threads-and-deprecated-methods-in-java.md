# Java 中绿色对本机线程和弃用方法

> 原文:[https://www . geesforgeks . org/green-vs-native-threads-and-弃用-methods-in-java/](https://www.geeksforgeeks.org/green-vs-native-threads-and-deprecated-methods-in-java/)

众所周知，多线程进程有几个控制序列，其中每个序列由一个线程控制，并且能够同时执行独立的任务。

在 Java 中，多线程概念是通过使用以下两种模型来实现的。
**1。青丝模型
2。原生螺纹模型**

***青丝模型***

*   在这个模型中，线程完全由 JVM **管理，没有任何种类的底层 OS 支持。**
*   这些线程在应用程序级别实现，并在用户空间中管理。
*   它们也被称为协作(用户级)线程。
*   一次只能处理一个绿色线程。因此，该模型被认为是**多对一**模型。因此，绿色线程可以在多核处理器上运行，但不能利用多核。
*   绿色线程的同步和资源共享更容易，因此执行时间也更少。
*   Sun Solaris 操作系统支持绿色线程模式。

***原生线程模型***

*   在底层操作系统支持的帮助下，该模型中的线程由 JVM **管理。**
*   这些线程在操作系统级别实现(通过使用操作系统多线程应用编程接口)，并在内核空间进行管理。
*   它们也被称为非绿色(内核级)线程。
*   多个本机线程可以共存。因此也被称为**多对多**模型。这种模型的这种特性允许它充分利用多核处理器，并在单独的内核上同时执行线程。
*   由于该模型允许多个线程同时执行，线程同步和资源共享变得复杂。这增加了线程的执行时间。
*   所有基于 windows 的操作系统都支持本机线程模型。

由于其局限性，**绿色线程模型被弃用，不再使用。**原生线程模型已经取代了绿色线程模型，在今天得到了广泛的应用。

除此之外，Java 中的 Thread 类还有一些不推荐使用的方法。

1.  **public void stop()**
    这个方法不推荐使用，因为使用起来本来就不安全。例如，假设一个线程已经打开了一个文件，并且正在写入该文件。突然，如果我们在这个线程上调用 stop()方法，那么线程会突然终止，文件会保持打开状态。
    这被认为是潜在的不安全。因此，我们使用线程间通信和中断系统来通知线程停止执行一段时间，而不是强制线程停止执行。
2.  **public void suspend()**
    thread . suspend()方法不推荐使用，因为它容易出现死锁。考虑一个例子，其中一个主线程持有一个对象的锁，并且该线程被挂起。在该线程恢复之前，没有其他线程可以获得该对象级锁。如果辅助线程试图在主线程恢复之前获取该对象的锁，那么就会出现死锁情况。
3.  **public void resume()**
    既然 suspend()方法不推荐使用，resume()方法也不推荐使用。

下面的例子说明了如何使用 suspend()方法可能导致**死锁。**

```
// Printer class
class Printer {

    // synchronized print() method
    public synchronized void print()
    {
        System.out.println(Thread.currentThread().getName() + 
                                           " wants to print");

        // making sure that primary thread is getting suspended
        if (Thread.currentThread().getName().equals("Primary Thread")) {
            System.out.println("Primary Thread has been suspended");
            Thread.currentThread().suspend();
            System.out.println("Primary Thread has been resumed");
        }

        System.out.println(Thread.currentThread().getName()
                           + " has finished printing");
    }
}

// Custom Thread class that extends Thread class
class CustomThread extends Thread {
    // string variable that will store name of the thread
    Printer obj;

    // constructor to initialize thread object
    CustomThread(String name, Printer p)
    {
        // calling Thread class constructor and naming
        // the thread
        super(name);
        obj = p;
    }

    // overridden run() method
    public void run()
    {
        // calling synchronized print() method
        obj.print();

        // printing a statement that confirms the 
        // end of execution of the thread
        System.out.println(this.getName() + 
                      " has finished its execution");
    }
}

// Driver class
class Deadlock {
    // Main method which thros InterruptedException 
    // that can be caused as we are calling sleep() method
    public static void main(String[] args) throws InterruptedException
    {
        // Creating Printer object in order to print
        Printer p = new Printer();

        // Creating primary thread and starting its execution
        CustomThread primary_thread = new CustomThread("Primary Thread", p);
        System.out.println("Primary Thread is starting its execution");
        primary_thread.start();

        // Making main thread to sleep for 1 second to make sure that
        // primary thread executes print() method and goes into suspend state
        Thread.sleep(2000);

        // Creating secondary thread and starting its execution
        CustomThread secondary_thread = new CustomThread("Secondary Thread", p);
        System.out.println("Secondary Thread is starting its execution");
        secondary_thread.start();
    }
}
```

**输出:**

```
Primary Thread is starting its execution
Primary Thread wants to print
Primary Thread has been suspended
Secondary Thread is starting its execution

```

**说明:**
在上面的程序中，我们创建了两个称为主线程和次线程的线程，并在 2 秒的时间间隔后按照各自的顺序启动这两个线程。

主线程首先被执行，并在执行 print()方法时被挂起。**在保持挂起状态的同时，拥有 Printer 类对象的锁。**之后，辅助线程尝试执行 print()方法。但是它不能执行它，因为 Printer 对象的锁是用主方法锁定的。

在这个阶段，两个线程都进入**死锁状态**，程序执行永远不会结束。我们可以看到，输出中只打印了 4 条语句，其余的语句没有打印，因为程序执行进入死锁状态。

**参考文献:**

1.  [多线程模型–甲骨文文档](https://docs.oracle.com/cd/E19455-01/806-3461/6jck06gqk/index.html)
2.  [不推荐使用的线程方法–甲骨文文档](https://docs.oracle.com/cd/E19455-01/806-3461/6jck06gr5/index.html)