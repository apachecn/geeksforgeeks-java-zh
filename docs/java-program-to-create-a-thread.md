# 创建线程的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序创建线程/](https://www.geeksforgeeks.org/java-program-to-create-a-thread/)

线程可以被称为轻量级进程。线程使用更少的资源在进程中创建和存在；线程共享进程资源。Java 的主线程是程序启动时启动的线程。从线程是由主线程创建的。这是完成执行的最后一个线程。

线程可以通过以下方式以编程方式创建:

1.  实现 [java.lang.Runnable](https://www.geeksforgeeks.org/runnable-interface-in-java/) 接口。
2.  扩展 [java.lang.Thread](https://www.geeksforgeeks.org/java-lang-thread-class-java/) 类。

您可以通过实现 runnable 接口并重写 run()方法来创建线程。然后，您可以创建一个线程对象并调用 start()方法。

**螺纹等级:**

Thread 类提供了用于创建和操作线程的构造函数和方法。该线程扩展了对象并实现了可运行接口。

```java
// start a newly created thread.
// Thread moves from new state to runnable state
// When it gets a chance, executes the target run() method
public void start()  
```

**可运行界面:**

任何具有旨在由线程执行的实例的类都应该实现 Runnable 接口。Runnable 接口只有一个方法，叫做 run()。

```java
// Thread action is performed
public void run() 
```

**创建线程的好处:**

*   与进程相比，Java Threads 更轻量级；创建线程花费的时间和资源更少。
*   线程共享其父进程的数据和代码。
*   线程通信比进程通信简单。
*   线程之间的上下文切换通常比进程之间的切换便宜。

**调用 run()而不是 start()**

常见的错误是使用 run()而不是 start()方法启动线程。

```java
  Thread myThread = new Thread(MyRunnable());
  myThread.run();  //should be start();
```

您创建的线程不调用 run()方法。相反，它被创建**神话**的线程调用。

**例 1:通过使用线程类**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;
class GFG extends Thread {
    public void run()
    {
        System.out.print("Welcome to GeeksforGeeks.");
    }
    public static void main(String[] args)
    {
        GFG g = new GFG(); // creating thread
        g.start(); // starting thread
    }
}
```

**Output**

```java
Welcome to GeeksforGeeks.
```

**示例 2:通过实现可运行接口**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;
class GFG implements Runnable {
    public static void main(String args[])
    {
        // create an object of Runnable target
        GFG gfg = new GFG();

        // pass the runnable reference to Thread
        Thread t = new Thread(gfg, "gfg");

        // start the thread
        t.start();

        // get the name of the thread
        System.out.println(t.getName());
    }
    @Override public void run()
    {
        System.out.println("Inside run method");
    }
}
```

**Output**

```java
gfg
Inside run method
```