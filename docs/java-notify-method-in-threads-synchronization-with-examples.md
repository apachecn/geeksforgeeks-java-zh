# 线程同步中的 Java notify()方法示例

> 原文:[https://www . geesforgeks . org/Java-notify-in-method-in-threads-synchronization-with-examples/](https://www.geeksforgeeks.org/java-notify-method-in-threads-synchronization-with-examples/)

*notify()方法*是在 Object 类中定义的，Object 类是 Java 的顶级类。它用于仅唤醒一个等待对象的线程，然后该线程开始执行。thread 类 notify()方法用于唤醒单个线程。如果多个线程正在等待通知，并且我们使用 notify()方法，那么只有一个线程会收到通知，其他线程将不得不等待更多的通知。此方法不返回值。

它与 wait()方法一起使用，以便在线程之间进行通信，因为通过 wait()方法进入等待状态的线程将一直存在，直到任何其他线程调用 [*notify()或 notifyAll()方法。*T3】](https://www.geeksforgeeks.org/difference-notify-notifyall-java/)

**语法:**

```
public final void notify() ; 
```

**实施:**

*   synchronized 关键字用于独占访问。
*   wait()指示调用线程关闭监视器并休眠，直到另一个线程进入监视器并调用 notify()。
*   notify()唤醒在同一对象上调用 wait()的第一个线程。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate notify() method in Thread
// Synchronization.

// Importing required classes
import java.io.*;
import java.util.*;

// Class 1
// Thread1
// Helper class extending Thread class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating object(thread) of class 2
        Thread2 objB = new Thread2();

        // Starting the thread
        objB.start();

        synchronized (objB)
        {

            // Try block to check for exceptions
            try {

                // Display message only
                System.out.println(
                    "Waiting for Thread 2 to complete...");

                // wait() method for thread to be in waiting
                // state
                objB.wait();
            }

            // Catch block to handle the exceptions
            catch (InterruptedException e) {

                // Print the exception along with line
                // number using printStackTrace() method
                e.printStackTrace();
            }

            // Print and display the total threads on the
            // console
            System.out.println("Total is: " + objB.total);
        }
    }
}
// Class 2
// Thread2
// Helper class extending Thread class
class Thread2 extends Thread {

    int total;

    // run() method  which is called automatically when
    // start() is initiated for the same
    // @Override
    public void run()
    {

        synchronized (this)
        {

            // iterating over using the for loo
            for (int i = 0; i < 10; i++) {

                total += i;
            }

            // Waking up the thread in waiting state
            // using notify() method
            notify();
        }
    }
}
```

**Output**

```
Waiting for Thread 2 to complete...
Total is: 45
```