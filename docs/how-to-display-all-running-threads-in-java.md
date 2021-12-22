# 如何在 Java 中显示所有正在运行的线程？

> 原文:[https://www . geesforgeks . org/如何显示所有运行中的 java 线程/](https://www.geeksforgeeks.org/how-to-display-all-running-threads-in-java/)

一个线程基本上是一个顺序执行的指令流。用于在程序中实现[多任务](https://www.geeksforgeeks.org/process-based-and-thread-based-multitasking/)。一个程序可以有多个线程。线程被用来同时做多件事情。线程基本上是用来在后台执行复杂的任务，不影响主程序。

在 Java 中显示所有正在运行的[线程有两种方法](https://www.geeksforgeeks.org/multithreading-in-java/)

### **1。使用线程组对象**

Java 为我们提供了一种在单个对象中对多个线程进行分组的方法。在 Java 中，一组线程，即线程组，是由线程组类实现的，所以这里我们将使用一个线程组对象来对当前运行的所有线程进行分组。在这之后，我们将使用线程组的 activeCount()方法来获取活动线程的数量，然后我们将使用线程组的 enumerate(Thread[] list)方法来复制数组中当前活动的线程，我们将循环数组来获取所有活动线程的名称。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to display all the running threads using
// ThreadGroup object

import java.io.*;

class GFGThread extends Thread {
    // overriden run method
    public void run()
    {
        System.out.println("Overriden Run Method");
    }
}

public class GFG {

    public static void main(String[] args)
    {
        // making a thread object
        GFGThread t1 = new GFGThread();
        GFGThread t2 = new GFGThread();
        t1.start(); // starting the thread
        t2.start();

        // getting the group of the threads/
        ThreadGroup threadGroup
            = Thread.currentThread().getThreadGroup();

        // getting the total active count of the threads
        int threadCount = threadGroup.activeCount();

        Thread threadList[] = new Thread[threadCount];
        // enumerating over the thread list
        threadGroup.enumerate(threadList);

        System.out.println("Active threads are:");

        // iterating over the for loop to get the names of
        // all the active threads.
        for (int i = 0; i < threadCount; i++)
            System.out.println(threadList[i].getName());
    }
}
```

### **2。使用 getAllStackTrace()方法**

getAllStackTrace()方法给出了所有正在运行的线程的堆栈跟踪。然后我们创建一组该元素的键，因为该方法返回一个映射，然后我们循环该组的所有元素以打印所有正在运行的线程。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to display all the running threads using
// getAllStackTraces() Method
import java.io.*;
import java.lang.*;
import java.util.*;

class GFGThread extends Thread {

    // overriden run method
    public void run()
    {
        System.out.println("Overriden Run Method");
    }
}

public class GFG {

    public static void main(String[] args)
    {
        // making a thread object
        GFGThread t1 = new GFGThread();
        GFGThread t2 = new GFGThread();
        t1.start(); // starting the thread
        t2.start();

        // getAllStackTraces() method will return the Set of
        // Thread Objects
        Set<Thread> threadSet
            = Thread.getAllStackTraces().keySet();
        // iterating over the threads to get the names of
        // all the active threads
        for (Thread x : threadSet) {
            System.out.println(x.getName());
        }
    }
}
```

**输出**

```
Overriden Run Method
Overriden Run Method
Thread-0
Reference Handler
Thread-1
Signal Dispatcher
main
Finalizer
```