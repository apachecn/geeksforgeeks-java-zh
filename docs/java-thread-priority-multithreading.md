# 多线程中的 Java 线程优先级

> 原文:[https://www . geesforgeks . org/Java-thread-priority-多线程/](https://www.geeksforgeeks.org/java-thread-priority-multithreading/)

正如我们已经知道的，完全面向对象的 java 在[多线程环境](https://www.geeksforgeeks.org/multithreading-in-java/)中工作，其中[线程调度器](https://www.geeksforgeeks.org/thread-scheduling/)根据线程的优先级将处理器分配给线程。每当我们在 Java 中创建一个线程时，它总是被赋予一些优先级。优先级可以由 JVM 在创建线程时给出，也可以由程序员明确给出。

[**<u>线程中的优先级</u>**](https://www.geeksforgeeks.org/java-thread-priority-multithreading/) 是一个概念，其中每个线程都有一个优先级，用外行人的语言来说，这里可以说每个对象都有优先级，用 1 到 10 的数字来表示。

*   默认优先级按预期设置为 5。
*   最低优先级设置为 1。
*   最大优先级设置为 10。

这里定义了 3 个常数，即:

1.  公共静态 int NORM_PRIORITY
2.  公共静态 int MIN_PRIORITY
3.  公共静态 int MAX_PRIORITY

让我们用一个例子来讨论一下如何在内部执行工作。在这里，我们将使用上面收集的知识，如下所示:

*   我们将使用[*<u>【current thread()</u>*](https://www.geeksforgeeks.org/naming-thread-fetching-name-current-thread-java/)方法获取当前线程的名称。用户也可以使用[*<u>setName()</u>*](https://www.geeksforgeeks.org/naming-thread-fetching-name-current-thread-java/)方法，如果他/她为了理解的目的想要按照选择来命名线程的话。
*   [*<u>getName()</u>*T5】方法](https://www.geeksforgeeks.org/method-class-getname-method-in-java/) 将用于获取线程的名称。

> 线程优先级的可接受值在 1 到 10 的范围内。

让我们讨论一下如何在 java 中获取和设置线程的优先级。

1.  **public final int getPriority():**Java . lang . thread . getPriority()方法返回给定线程的优先级。
2.  **public final void setPriority(int newPriority):**Java . lang . thread . setPriority()方法将线程的优先级改为 new priority 值。如果参数 newPriority 的值超过最小(1)和最大(10)限制，此方法将引发 IllegalArgumentException。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Priorities in Multithreading
// via help of getPriority() and setPriority() method

// Importing required classes
import java.lang.*;

// Main class
class ThreadDemo extends Thread {

    // Method 1
    // run() method for the thread that is called
    // as soon as start() is invoked for thread in main()
    public void run()
    {
        // Print statement
        System.out.println("Inside run method");
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Creating random threads
        // with the help of above class
        ThreadDemo t1 = new ThreadDemo();
        ThreadDemo t2 = new ThreadDemo();
        ThreadDemo t3 = new ThreadDemo();

        // Thread 1
        // Display the priority of above thread
        // using getPriority() method
        System.out.println("t1 thread priority : "
                           + t1.getPriority());

        // Thread 1
        // Display the priority of above thread
        System.out.println("t2 thread priority : "
                           + t2.getPriority());

        // Thread 3
        System.out.println("t3 thread priority : "
                           + t3.getPriority());

        // Setting priorities of above threads by
        // passing integer arguments
        t1.setPriority(2);
        t2.setPriority(5);
        t3.setPriority(8);

        // t3.setPriority(21); will throw
        // IllegalArgumentException

        // 2
        System.out.println("t1 thread priority : "
                           + t1.getPriority());

        // 5
        System.out.println("t2 thread priority : "
                           + t2.getPriority());

        // 8
        System.out.println("t3 thread priority : "
                           + t3.getPriority());

        // Main thread

        // Displays the name of
        // currently executing Thread
        System.out.println(
            "Currently Executing Thread : "
            + Thread.currentThread().getName());

        System.out.println(
            "Main thread priority : "
            + Thread.currentThread().getPriority());

        // Main thread priority is set to 10
        Thread.currentThread().setPriority(10);

        System.out.println(
            "Main thread priority : "
            + Thread.currentThread().getPriority());
    }
}
```

**Output**

```java
t1 thread priority : 5
t2 thread priority : 5
t3 thread priority : 5
t1 thread priority : 2
t2 thread priority : 5
t3 thread priority : 8
Currently Executing Thread : main
Main thread priority : 5
Main thread priority : 10
```

输出解释:

*   优先级最高的线程将比其他线程先获得执行机会。假设有 3 个线程 t1、t2 和 t3，优先级分别为 4、6 和 1。因此，线程 t2 将首先基于最大优先级 6 执行，然后 t1 执行，然后 t3 执行。
*   主线程的默认优先级总是 5，稍后可以更改。所有其他线程的默认优先级取决于父线程的优先级。

现在，极客们，你们一定想知道，如果我们给线程分配相同的优先级，会发生什么。为了照顾线程，所有的处理都是在线程调度器的帮助下进行的。我们可以参考下面的例子，如果优先级设置为相同，会发生什么，稍后我们将讨论它作为输出解释，以便在概念和实践上有更好的理解。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate that a Child thread
// Getting Same Priority as Parent thread

// Importing all classes from java.lang package
import java.lang.*;

// Main class
// ThreadDemo
// Extending Thread class
class GFG extends Thread {

    // Method 1
    // run() method for the thread that is
    // invoked as threads are started
    public void run()
    {
        // Print statement
        System.out.println("Inside run method");
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // main thread priority is set to 6 now
        Thread.currentThread().setPriority(6);

        // Current thread is accessed
        // using currentThread() method

        // Print and display main thread priority
        // using getPriority() method of Thread class
        System.out.println(
            "main thread priority : "
            + Thread.currentThread().getPriority());

        // Creating a thread by creating object inside
        // main()
        GFG t1 = new GFG();

        // t1 thread is child of main thread
        // so t1 thread will also have priority 6

        // Print and display priority of current thread
        System.out.println("t1 thread priority : "
                           + t1.getPriority());
    }
}
```

**Output**

```java
main thread priority : 6
t1 thread priority : 6
```

输出解释:

*   如果两个线程具有相同的优先级，那么我们不能期望哪个线程将首先执行。这取决于线程调度器的算法(循环、先到先得等)
*   如果我们使用线程优先级进行线程调度，那么我们应该始终牢记底层平台应该提供基于线程优先级的调度支持。

所有这些处理都是在线程调度器的帮助下进行的，在下面提供的视频示例的帮助下，可以更好地可视化线程调度器:

本文由**达尔梅什·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。