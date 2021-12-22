# 如何在 Java 中获取当前运行线程的 Id？

> 原文:[https://www . geesforgeks . org/如何获取当前运行的 java 线程 id/](https://www.geeksforgeeks.org/how-to-get-the-id-of-a-current-running-thread-in-java/)

[线程](https://www.geeksforgeeks.org/java-lang-thread-class-java/)类的 **getId()** 方法返回被调用线程的标识符。线程标识是创建该线程时生成的长正数。线程标识是唯一的，并且在其生存期内保持不变。当一个线程被终止时，这个线程标识可以被重用。

Java 允许在线程的帮助下并行执行程序的不同部分。Java 中的多线程是通过扩展线程类或实现可运行接口来实现的。由于 Java 中不允许多重继承，所以建议实现 [Runnable](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/runnable-interface-in-java/&sa=U&ved=2ahUKEwjCvt6GnPXsAhXlzTgGHcmTAqQQFjAAegQIAhAC&usg=AOvVaw0TRoYGJUHtw6zRt_e3w3_z) 接口来创建线程，这样如果需要，实现 Runnable 接口的类可以扩展一些其他类。在本文中，我们已经演示了创建线程的两种方法。第一种方法通过扩展 thread 类显示线程创建，第二种方法通过实现 Runnable Interface 显示线程创建。

**申报**T0】

**返回值:** 这个方法返回一个线程的 ID。

**方法 1:** 以下是通过[扩展线程类](https://www.geeksforgeeks.org/multithreading-in-java/)来创建线程的步骤。

1.  The ThreadDemo1 class extends the Thread class and covers the run () method of the Thread class.
2.  In the run () method, we use **currentthread (). The method gets the name of the current thread that called the run () method.**
3.  We use **currentthread (). Getid ()** method gets the Id of the current thread that called the run () method.
4.  In the main () method, two instances of the ThreadDemo1 class are created.
5.  T1 and t2 are two threads that call the start () method.
6.  Calling the start () method basically calls the run () method by default.
7.  [join ()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/joining-threads-in-java/&sa=U&ved=2ahUKEwiD9pvDnPXsAhX2wzgGHXZ_CpAQFjAAegQIBhAC&usg=AOvVaw2qO1RJmoIjTBfEDQ9uzBnG) method is used to prevent T2 from running before t1 is completed.
8.  As soon as t1 completes T2, it will be executed.

**示例:**

## Java

```
// Java program to get the id of a 
// thread

import java.util.*;
public class ThreadDemo1 extends Thread {
    public void run()
    {
        // gets the name of current thread
        System.out.println(
            "Current Thread Name: "
            + Thread.currentThread().getName());

        // gets the ID of the current thread
        System.out.println(
            "Current Thread ID: "
            + Thread.currentThread().getId());
    }
    public static void main(String[] args)
        throws InterruptedException
    {
        Scanner s = new Scanner(System.in);

        // creating first thread
        ThreadDemo1 t1 = new ThreadDemo1();

        // creating second thread
        ThreadDemo1 t2 = new ThreadDemo1();

        // Starting the thread
        t1.start();
        t2.start();

        // t2 does not start execution until t1 completes
        // execution
        t1.join();
    }
}
```

**输出**

```
Current Thread Name: Thread-0
Current Thread Name: Thread-1
Current Thread ID: 11
Current Thread ID: 12

```

**方法 2:** 在第二种方法中，通过实现**可运行**接口来创建线程。

1.  The ThreadDemo2 class implements the Runnable interface and overrides the run () method.
2.  A runnable instance of thread demo class 2 T is created.
3.  Two instances of the Thread class are created by passing the runnable instance as the first parameter and the thread name as the second parameter.
4.  The start () method is called on two threads.
5.  The start () method calls the run () method by default.

**示例:**

## Java

```
// Java program to get the id of a 
// thread

public class ThreadDemo2 implements Runnable {
    public void run()
    {
        // gets the name of current thread
        System.out.println(
            "Current Thread Name: "
            + Thread.currentThread().getName());

        // gets the ID of the current thread
        System.out.println(
            "Current Thread ID: "
            + Thread.currentThread().getId());
    }
    public static void main(String[] args)
    {
          // Runnable target
        ThreadDemo2 t = new ThreadDemo2();

          // create threads
        Thread t1 = new Thread(t, "First Thread");
        Thread t2 = new Thread(t, "Second Thread");

          // start threads
        t1.start();
        t2.start();
    }
}
```

**输出**

```
Current Thread Name: First Thread
Current Thread Name: Second Thread
Current Thread ID: 11
Current Thread ID: 12

```

**注意:**第二种方法的输出可能会有所不同，因为它不是[同步的](https://www.geeksforgeeks.org/synchronized-in-java/)，并且线程是并发执行的。因此，线程名称或线程 id 的打印顺序可能会有所不同。为了防止这个问题，我们在第一种方法中使用了 [join()](https://www.geeksforgeeks.org/joining-threads-in-java/#:~:text=Thread%20class%20provides%20the%20join,is%20executed%20by%20the%20program.) 方法。如果要保持打印输出的顺序，那么用户可以使用 join()方法。