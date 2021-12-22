# Java 中的原子变量示例

> 原文:[https://www . geesforgeks . org/atomic-variables-in-Java-with-examples/](https://www.geeksforgeeks.org/atomic-variables-in-java-with-examples/)

在 [**多线程**](https://www.geeksforgeeks.org/multi-threading-models-in-process-management/) 中，共享实体在合并[并发](https://www.geeksforgeeks.org/java-concurrency-yield-sleep-and-join-methods/)时大多会导致问题。共享实体，例如，**可变的**对象或变量，可能会被更改，这可能会导致程序或[数据库](https://www.geeksforgeeks.org/dbms/)的不一致。因此，处理并发访问的共享实体变得至关重要。在这种情况下，**原子变量**可以是备选方案之一。

Java 提供[](https://www.geeksforgeeks.org/tag/java-util-concurrent-atomic-package/)**原子类，如 [AtomicInteger](https://www.geeksforgeeks.org/tag/java-atomicinteger/) 、 [AtomicLong](https://www.geeksforgeeks.org/tag/java-atomiclong/) 、 [AtomicBoolean](https://www.geeksforgeeks.org/tag/java-atomicboolean/) 和 **AtomicReference** 。这些类的对象分别表示 int、long、boolean 和 object reference 的**原子变量**。这些类包含以下方法。**

1.  ****设置(int 值):**设置给定值**
2.  ****get():** 获取当前值**
3.  ****lazySet(int 值):**最终设置为给定值**
4.  ****比较数据集(int expect，int update):** 如果当前值==期望值，则自动将该值设置为给定的更新值**
5.  ****addAndGet(int delta):** 自动将给定值加到当前值上**
6.  ****递减和获取():**自动将当前值递减 1**

****示例:****

```java
// Atomic Variable
AtomicInteger var;
```

****需要原子变量**
考虑下面的例子:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
class Counter extends Thread {

    // Counter Variable
    int count = 0;

    // method which would be called upon
    // the start of execution of a thread
    public void run()
    {
        int max = 1_000_00_000;

        // incrementing counter
        // total of max times
        for (int i = 0; i < max; i++) {
            count++;
        }
    }
}

public class UnSafeCounter {
    public static void main(String[] args)
        throws InterruptedException
    {
        // Instance of Counter Class
        Counter c = new Counter();

        // Defining Two different threads
        Thread first = new Thread(c, "First");
        Thread second = new Thread(c, "Second");

        // Threads start executing
        first.start();
        second.start();

        // main thread will wait for
        // both threads to get completed
        first.join();
        second.join();

        // Printing final value of count variable
        System.out.println(c.count);
    }
}
```

****Output:** 

```java
137754082
```** 

**在单线程环境中，上述类只会给出预期的结果。但是当涉及多线程环境时，可能会导致不一致的结果。发生这种情况是因为更新“var”分三步完成:读取、更新和写入。如果两个或多个线程试图同时更新该值，则它可能无法正确更新。**

**使用[锁定和同步](https://www.geeksforgeeks.org/lock-framework-vs-thread-synchronization-in-java/)可以解决这个问题，但是效率不高。**

****1。使用锁类比或同步:**同步或锁定可以解决我们的问题，但它会损害时间效率或性能。首先，它要求资源和线程调度器控制锁。第二，当多个线程试图获取锁时，只有一个线程获胜，其余的线程被挂起或阻塞。挂起或阻塞线程会对性能产生巨大影响。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import java.io.*;
import java.util.concurrent.locks.*;

class Counter extends Thread {

    // Counter Variable
    int count = 0;

    // method which would be called upon
    // the start of execution of a thread
    public synchronized void run()
    {

        int max = 1_000_00_000;

        // incrementing counter total of max times
        for (int i = 0; i < max; i++) {
            count++;
        }
    }
}

public class SynchronizedCounter {
    public static void main(String[] args)
        throws InterruptedException
    {
        // Instance of Counter Class
        Counter c = new Counter();

        // Defining Two different threads
        Thread first = new Thread(c, "First");
        Thread second = new Thread(c, "Second");

        // Threads start executing
        first.start();
        second.start();

        // main thread will wait for both
        // threads to complete execution
        first.join();
        second.join();

        // Printing final value of count variable
        System.out.println(c.count);
    }
}
```

****Output:** 

```java
200000000
```** 

****2。使用原子变量:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import java.util.concurrent.atomic.AtomicInteger;

class Counter extends Thread {

    // Atomic counter Variable
    AtomicInteger count;

    // Constructor of class
    Counter()
    {
        count = new AtomicInteger();
    }

    // method which would be called upon
    // the start of execution of a thread
    public void run()
    {

        int max = 1_000_00_000;

        // incrementing counter total of max times
        for (int i = 0; i < max; i++) {
            count.addAndGet(1);
        }
    }
}

public class AtomicCounter {
    public static void main(String[] args)
        throws InterruptedException
    {
        // Instance of Counter Class
        Counter c = new Counter();

        // Defining Two different threads
        Thread first = new Thread(c, "First");
        Thread second = new Thread(c, "Second");

        // Threads start executing
        first.start();
        second.start();

        // main thread will wait for both
        // threads to complete execution
        first.join();
        second.join();

        // Printing final value of count variable
        System.out.println(c.count);
    }
}
```

****Output:** 

```java
200000000
```**