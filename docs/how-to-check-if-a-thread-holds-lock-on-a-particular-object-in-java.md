# 如何在 Java 中检查线程是否持有特定对象的锁？

> 原文:[https://www . geeksforgeeks . org/如何检查线程是否锁定 java 中的特定对象/](https://www.geeksforgeeks.org/how-to-check-if-a-thread-holds-lock-on-a-particular-object-in-java/)

Java 语言是多年来最流行的语言之一。java 编程最有利的特性之一是多线程。多线程允许将单个程序执行到程序的许多小部分中，从而最大限度地利用 CPU。线程是一个轻量级的进程，有助于高效地执行并发的大型进程。但是有时这些线程会降低程序的效率。

让我们举一个真实的例子来说明为什么多线程概念的无效使用会导致程序效率和资源的降低。

> **真实例子**
> 
> 考虑一个有学生的班级，一个老师正在教他们把一个老师视为一个线索，因为学生的考试即将到来，几乎所有不同的老师(Mutlthreads)都试图尽可能多地教学，所以他们一个接一个地随机教学，以尽快完成教学大纲。

这可能会减少教师的任务，即完成他们的任务，但学生的负担会增加太多。为了解决这种情况，我们必须同步教师的时间，即线程，以便学生之间的混乱可以减少。类似地，在 java 中，我们可以同步访问特定资源(函数)的线程，这意味着锁定资源，以便一次只有一个资源可以访问它们。在本文中，我们将讨论如何检查线程是否持有 java 中特定对象的锁。

***holdLock()方法*** 用于在 java 程序执行期间检查特定对象上的锁

**参数:**这个方法取类的引用/对象，我们要在其中检查线程上是否存在锁。

**返回类型:**该方法返回布尔参数，即真或假。True 表示当前对象上可用的监视器锁定。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Illustrating How to Check if a Thread Holds
// Lock on a Particular Object

// Importing the libraries
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Creating the constructor
    GFG()
    {

        // Checking the status of the lock on the object
        System.out.println(Thread.holdsLock(this));

        // Synchronizing the thread
        synchronized (this)
        {

            // Checking the status of the lock on the object
            // using holdsLock() method over
            // same thread using this keyword
            System.out.println(Thread.holdsLock(this));
        }
    }

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a Thread class object
        Thread ob = new Thread() {
            // run() method for this thread which
            // is invoked as start() method is invoked
            public void run()
            {

                // Creating a class object
                // inside the run() methodof the class
                GFG ob1 = new GFG();
            }
        };

        // Starting the thread with
        // the help of start() method
        ob.start();
    }
}
```

**Output**

```java
false
true
```