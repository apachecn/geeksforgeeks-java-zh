# 在 Java 中命名一个线程并获取当前线程的名称

> 原文:[https://www . geesforgeks . org/naming-thread-取数-name-current-thread-java/](https://www.geeksforgeeks.org/naming-thread-fetching-name-current-thread-java/)

线程可以被称为轻量级进程。线程使用更少的资源在进程中创建和存在；线程共享进程资源。Java 的主线程是程序启动时启动的线程。现在让我们讨论一下用什么方法命名一个线程的古怪概念。

**方法:**我们可以通过两种方式来设置名称，可以是直接设置，也可以是间接设置，我们将通过这两种方式来查看名称。

1.  Create a thread and pass the thread name (direct method)
2.  Use the setName () method of the thread class (indirect method)

**方法 1:** 创建线程并传递线程的名称

它是 java 中一种直接命名线程的方法，每个线程都有一个名字，那就是:Thread-0，Thread-1，Thread-2，…。等等。Java 提供了一些改变线程名称的方法。设置线程名基本上有两种方法。这两种方法都在 [java.lang.Thread 类](https://www.geeksforgeeks.org/java-lang-thread-class-java/)中定义。

极客，现在你一定想知道如何直接设置线程的名称？在 java 中，我们可以在创建线程时设置线程名称，并绕过线程名称作为参数，如下例所示:

**示例:**

## Java

```
// Java Program Illustrating How to Set the name
// of Thread at time of Creation

// Importing I/O classes from java.io package
import java.io.*;

// Class 1
// Helper class
class ThreadNaming extends Thread {

    // Parametrized constructor
    ThreadNaming(String name)
    {
        // Call to constructor of
        // the Thread class as super keyword
        // refers to parent class
        super(name);
    }

    // run() method for thread
    @Override public void run()
    {
        // Print statement when thread is called inside
        // main()
        System.out.println("Thread is running.....");
    }
}

// Class 2
// Main class
class GFG {

    // main driver method
    public static void main(String[] args)
    {

        // Creating two threads
        ThreadNaming t1 = new ThreadNaming("geek1");
        ThreadNaming t2 = new ThreadNaming("geek2");

        // Getting the above created threads names.
        System.out.println("Thread 1: " + t1.getName());
        System.out.println("Thread 2: " + t2.getName());

        // Starting threads using start() method
        t1.start();
        t2.start();
    }
}
```

**输出**

```
Thread 1: geek1
Thread 2: geek2
Thread is running.....
Thread is running.....
```

**方式二:** [使用线程类](https://www.geeksforgeeks.org/naming-thread-fetching-name-current-thread-java/)的 setName()方法

我们可以通过调用线程对象上的 setName 方法来设置(更改)线程的名称。它将更改线程的名称。

**语法:**

```
public final void setName(String name)
```

**参数:**指定线程名称的字符串

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Illustrating How to Get and Change the
// Name of a Thread

// Importing input output classes
import java.io.*;

// Class 1
// Helper class extending Thread class
class ThreadNaming extends Thread {

    // run() method for thread which is called
    // as soon as start() is called over threads
    @Override public void run()
    {

        // Print statement when run() is called over thread
        System.out.println("Thread is running.....");
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating two threads via above class
        // as it is extending Thread class
        ThreadNaming t1 = new ThreadNaming();
        ThreadNaming t2 = new ThreadNaming();

        // Fetching the above created threads names
        // using getName() method
        System.out.println("Thread 1: " + t1.getName());
        System.out.println("Thread 2: " + t2.getName());

        // Starting threads using start() method
        t1.start();
        t2.start();

        // Now changing the name of threads
        t1.setName("geeksforgeeks");
        t2.setName("geeksquiz");

        // Again getting the new names of threads
        System.out.println(
            "Thread names after changing the "
            + "thread names");

        // Printing the above names
        System.out.println("New Thread 1 name:  "
                           + t1.getName());
        System.out.println("New Thread 2 name: "
                           + t2.getName());
    }
}
```

**Output**

```
Thread 1: Thread-0
Thread 2: Thread-1
Thread is running.....
Thread names after changing the thread names
New Thread 1 name:  geeksforgeeks
New Thread 2 name: geeksquiz
Thread is running.....
```

## **如何获取当前线程的名称？**

现在让我们详细讨论获取当前线程的名称。我们可以在创建线程时获取当前线程的名称，并绕过线程的名称作为参数。

**方法:**T2【currentThread()

它是在 java.langThread 类中定义的。

**返回类型:**返回对当前执行线程的引用

**语法:**

```
public static Thread currentThread()
```

**示例:**

## Java

```
// Java program to Illustrate How to Get Name of
// Current Executing thread
// Using getName() Method

// Importing reqiored I/O classes
import java.io.*;

// Class 1
// Helper class extending to Thread class
class ThreadNaming extends Thread {

    // run() method for this thread
    @Override public void run()
    {
        // Display message
        System.out.println(
            "Fetching current thread name..");

        // Getting the current thread name
        // using getname() method
        System.out.println(
            Thread.currentThread().getName());
    }
}

// Class 2
// Main class
class GFG {

    // Main method driver
    public static void main(String[] args)
    {

        // Creating two threads inside main() method
        ThreadNaming t1 = new ThreadNaming();
        ThreadNaming t2 = new ThreadNaming();

        // Starting threads using start() method which
        // automatically calls run() method
        t1.start();
        t2.start();
    }
}
```

**输出**

```
Fetching current thread name..
Thread-0
Fetching current thread name..
Thread-1
```

本文由 **Nitsdheerendra** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。