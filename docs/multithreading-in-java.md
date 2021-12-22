# Java 中的多线程

> 原文:[https://www.geeksforgeeks.org/multithreading-in-java/](https://www.geeksforgeeks.org/multithreading-in-java/)

多线程是一种 Java 特性，它允许同时执行程序的两个或多个部分，以最大限度地利用 CPU。这种程序的每个部分都称为一个线程。因此，线程是进程中的轻量级进程。

可以使用两种机制创建线程:

1.  扩展线程类
2.  实现可运行接口

**通过扩展线程类**
来创建线程我们创建了一个扩展 **java.lang.Thread** 类的类。此类重写线程类中可用的 run()方法。线程在 run()方法中开始它的生命。我们创建一个新类的对象，并调用 start()方法来启动线程的执行。Start()调用 Thread 对象上的 run()方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code for thread creation by extending
// the Thread class
class MultithreadingDemo extends Thread {
    public void run()
    {
        try {
            // Displaying the thread that is running
            System.out.println(
                "Thread " + Thread.currentThread().getId()
                + " is running");
        }
        catch (Exception e) {
            // Throwing an exception
            System.out.println("Exception is caught");
        }
    }
}

// Main Class
public class Multithread {
    public static void main(String[] args)
    {
        int n = 8; // Number of threads
        for (int i = 0; i < n; i++) {
            MultithreadingDemo object
                = new MultithreadingDemo();
            object.start();
        }
    }
}
```

**Output**

```
Thread 15 is running
Thread 14 is running
Thread 16 is running
Thread 12 is running
Thread 11 is running
Thread 13 is running
Thread 18 is running
Thread 17 is running

```