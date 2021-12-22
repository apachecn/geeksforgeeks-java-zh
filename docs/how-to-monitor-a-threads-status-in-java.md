# 如何在 Java 中监控线程的状态？

> 原文:[https://www . geesforgeks . org/how-monitor-a-threads-status-in-Java/](https://www.geeksforgeeks.org/how-to-monitor-a-threads-status-in-java/)

Java 语言通过使用监视器支持线程同步。监视器与特定的数据项相关联，并充当该数据的锁。当一个线程持有某个数据项的监视器时，其他线程被锁定，不能检查或修改数据。为了监控一个线程的状态，Java 有预定义的 [*方法，该方法由线程类扩展。java.lang.reflect.Method 类的*](https://www.geeksforgeeks.org/naming-thread-fetching-name-current-thread-java/) *[*getName()方法*](https://www.geeksforgeeks.org/method-class-getname-method-in-java/) 用于获取实体的名称，作为 String，该实体可以是类、接口、数组、枚举、方法等。类对象的。[<u>j</u>ava . lang . reflect](https://www.geeksforgeeks.org/reflection-in-java/)的 **getName()** 方法。方法类有助于获取方法的名称，如字符串。要获取一个类的所有方法的名称，请获取该类对象的所有方法。然后在这些方法对象上调用 getName()。*

**语法:**

```java
public String getName()
```

**返回值:**返回方法名，字符串形式。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Monitor a Thread's Status

// Class 1
// Helper class
class MyThread extends Thread {

    // Initially initializing states using boolean methods
    boolean waiting = true;
    boolean ready = false;

    // Constructor of this class
    MyThread() {}

    // Methods of this class are as follows:

    // Method 1
    synchronized void startWait()
    {
        try {
            while (!ready)
                wait();
        }
        catch (InterruptedException exc) {
            System.out.println("wait() interrupted");
        }
    }

    // Method 2
    synchronized void notice()
    {
        ready = true;
        notify();
    }

    // Method 3
    // To run threads when called using start()
    public void run()
    {

        // Getting the name of current thread
        // using currentThread() and getName() methods
        String thrdName = Thread.currentThread().getName();

        // Print the corresponding thread
        System.out.println(thrdName + " starting.");

        // While the thread is in waiting state
        while (waiting)
            System.out.println("waiting:" + waiting);

        // Display message
        System.out.println("waiting...");

        // calling the Method1
        startWait();

        // Try block to check for exceptions
        try {

            // Making thread to pause execution for a
            // certain time of 1 second using sleep() method
            Thread.sleep(1000);
        }

        // Catch block to handle the exceptions
        catch (Exception exc) {

            // Display if interrupted
            System.out.println(thrdName + " interrupted.");
        }

        // Else display the thread is terminated.
        System.out.println(thrdName + " terminating.");
    }
}

// Class 2
// Main class
public class GFG {

    // Method 1
    // To get the thread status
    static void showThreadStatus(Thread thrd)
    {
        System.out.println(thrd.getName()
                           + "  Alive:=" + thrd.isAlive()
                           + " State:=" + thrd.getState());
    }

    // Method 2
    // Main driver method
    public static void main(String args[]) throws Exception
    {

        // Creating an object of our thread class
        // in the main() method
        MyThread thrd = new MyThread();

        // Setting the name for the threads
        // using setname() method
        thrd.setName("MyThread #1");

        // getting the status of current thread
        showThreadStatus(thrd);

        // Starting the thread which automatically invokes
        // the run() method for the thread
        thrd.start();

        // Similarly repeating the same
        Thread.sleep(50);
        showThreadStatus(thrd);

        // hee notice we change the flag value
        // thai is no more in waiting state now
        thrd.waiting = false;

        Thread.sleep(50);
        showThreadStatus(thrd);
        thrd.notice();

        Thread.sleep(50);
        showThreadStatus(thrd);

        // Till thread is alive
        while (thrd.isAlive())

            // Print the statement
            System.out.println("alive");

        // Callin the method
        showThreadStatus(thrd);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-593642-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210423141355/thread_status.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210423141355/thread_status.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210423141355/thread_status.mp4)</video>