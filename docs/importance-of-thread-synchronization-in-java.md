# Java 中线程同步的重要性

> 原文:[https://www . geesforgeks . org/Java 中线程同步的重要性/](https://www.geeksforgeeks.org/importance-of-thread-synchronization-in-java/)

我们的系统在多线程环境中工作，这成为操作系统更好地利用资源的重要部分。同时运行程序的两个或多个部分的过程称为多线程。程序是一组指令，其中多个进程正在运行，并且在一个进程中，多个线程正在工作。线程只不过是轻量级进程。例如，在电脑里，我们一边玩电子游戏，一边用微软 word 工作，听音乐。所以，这些是我们正在同时进行的过程。在这种情况下，每个应用程序都有多个子进程，即线程。在前面的例子中，我们听音乐，其中我们有一个音乐播放器作为一个应用程序，它包含多个运行的子进程，如管理播放列表、访问互联网等。因此，线程是要执行的任务，多线程是在同一程序中同时执行多个任务/进程。

这是多线程的基本介绍，将进一步帮助理解线程同步的重要性。

**线程优先级**

在 java 中，每个线程都被赋予一个优先级，这个优先级决定了线程之间应该如何相互处理。线程的优先级用于决定何时从一个正在运行的线程切换到下一个线程。优先级较高的线程可以抢占优先级较低的线程，并且可能会占用更多的 CPU 时间。简单地说，与优先级较低的线程相比，优先级较高的线程首先获得资源。但是，在这种情况下，当两个具有相同优先级的线程想要相同的资源时，情况就会变得更加复杂。因此，在多线程环境中，如果具有相同优先级的线程使用相同的资源，就会产生不必要的结果或错误的代码。

举个例子吧。在一个房间里，我们有多台计算机连接到一台打印机上。有一次，一台计算机想要打印一份文件，所以它使用了打印机。同时，另一台计算机希望打印机打印其文档。因此，两台计算机需要相同的资源，即打印机。因此，如果两个进程一起运行，那么打印机将打印一台计算机和另一台计算机的文档。这将产生无效输出。现在，如果两个具有相同优先级或想要相同资源的线程导致不一致的输出，那么在线程的情况下也会发生同样的事情。

在 java 中，当两个或多个线程试图同时访问同一资源时，会导致 java 运行时缓慢执行一个或多个线程，甚至暂停它们的执行。为了克服这个问题，我们有线程同步。

[同步](https://www.geeksforgeeks.org/synchronized-in-java/) 表示多个进程/线程之间的协调。

**同步类型:**

同步有两种类型，如下所示:

1.  进程同步
2.  线程同步

这里我们将主要关注线程同步。

线程同步基本上是指到一次执行一个线程，其余线程处于[等待状态](https://www.geeksforgeeks.org/lifecycle-and-states-of-a-thread-in-java/)的概念。这个过程被称为线程同步。防止了线程干扰和不一致的问题。

使用[锁或监控](https://www.geeksforgeeks.org/difference-between-lock-and-monitor-in-java-concurrency/)建立同步。在 Java 中，监视器是用作互斥锁的对象。一次只有一个线程有权拥有监视器。当一个线程获得一个锁，那么所有其他试图获取锁定监视器的线程将被挂起。因此，其他线程被认为在等待监视器，直到第一个线程退出监视器。简单地说，当一个线程请求一个资源时，这个资源就会被锁定，这样在这个资源被释放之前，其他线程就不能工作或进行任何修改。

**线程同步有两种类型:**

1.  **互斥**
2.  [**线程间通信**](https://www.geeksforgeeks.org/inter-thread-communication-java/)

**A.** **互斥**

当共享任何资源时，这将保持线程相互干扰，即互斥。我们可以通过

*   同步方法
*   同步块
*   静态同步

**同步法**

我们可以使用[](https://www.geeksforgeeks.org/synchronized-in-java/)***关键字将一个方法声明为同步。这将使在方法内部编写的代码线程安全，以便在共享资源时不会有其他线程执行。***

*****实施:*****

***我们将建议同时打印两个线程，显示没有线程同步的异步行为。***

*****例 1:*****

## ***Java 语言(一种计算机语言，尤用于创建网站)***

```java
***// Class 1
// Helper class
// Extending Thread class
public class PrintTest extends Thread {

    // Non synchronized Code

    // Method 1
    public void printThread(int n)
    {

        // This loop will print the  currently executed
        // thread
        for (int i = 1; i <= 10; i++) {
            System.out.println("Thread " + n
                               + " is working...");

            // Try block to check for exceptions
            try {

                // Pause the execution of current thread
                // for 0.600 seconds using sleep() method
                Thread.sleep(600);
            }

            // Catch block to handle the exceptions
            catch (Exception ex) {

                // Overriding existing toString() method and
                // prints exception if occur
                System.out.println(ex.toString());
            }
        }

        // Display message for better readability
        System.out.println("--------------------------");

        try {

            // Pause the execution of current  thread
            // for 0.1000 millisecond or 1sec using sleep
            // method
            Thread.sleep(1000);
        }

        catch (Exception ex) {

            // Printing the exception
            System.out.println(ex.toString());
        }
    }
}

// Class 2
// Helper class extending Thread Class
public class Thread1 extends Thread {

    // Declaring variable of type Class1
    PrintTest test;

    // Constructor for class1
    Thread1(PrintTest p) { test = p; }

    // run() method of this class for
    // entry point for thread1
    public void run()
    {

        // Calling method  1 as in above class
        test.printThread(1);
    }
}

// Class 3
// Helper class extending Thread Class
public class Thread2 extends Thread {

    // Declaring variable of type Class1
    PrintTest test;

    // Constructor for class2
    Thread2(PrintTest p) { test = p; }

    // run() method of this class for
    // entry point for thread2
    public void run() { test.printThread(2); }
}

// Class 4
// Main class
public class SynchroTest {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of class 1 inside main() method
        PrintTest p = new PrintTest();

        // Passing the same object of class PrintTest to
        // both threads
        Thread1 t1 = new Thread1(p);
        Thread2 t2 = new Thread2(p);

        // Start executing the threads
        // using start() method
        t1.start();
        t2.start();

        // This will print both the threads  simultaneously
    }
}***
```

*****输出:*****

***<video class="wp-video-shortcode" id="video-665021-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210823113636/syn1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210823113636/syn1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210823113636/syn1.mp4)</video>***

> ***现在使用 synchronized 方法，它将锁定共享资源的对象，并给出一致的输出。***

*****例 2:*****

## ***Java 语言(一种计算机语言，尤用于创建网站)***

```java
***// Java Program Illustrating Lock the Object for
// the shared resource giving consistent output

// Class 1
// Helper class extending Thread class
public class PrintTest extends Thread {

    // synchronized code
    // synchronized method will lock the object and
    // releases when thread is terminated or completed its
    // execution.
    synchronized public void printThread(int n)
    {
        for (int i = 1; i <= 10; i++) {
            System.out.println("Thread " + n
                               + " is working...");

            try {

                // pause the execution of current  thread
                // for 600 millisecond
                Thread.sleep(600);
            }
            catch (Exception ex) {
                // overrides toString() method  and prints
                // exception if occur
                System.out.println(ex.toString());
            }
        }
        System.out.println("--------------------------");
        try {

            // pause the execution of current  thread for
            // 1000 millisecond
            Thread.sleep(1000);
        }
        catch (Exception ex) {
            System.out.println(ex.toString());
        }
    }
}
// creating thread1 extending Thread Class

public class Thread1 extends Thread {

    PrintTest test;
    Thread1(PrintTest p) { test = p; }

    public void run() // entry point for thread1
    {

        test.printThread(1);
    }
}
// creating thread2 extending Thread Class

public class Thread2 extends Thread {

    PrintTest test;
    Thread2(PrintTest p) { test = p; }
    public void run() // entry point for thread2
    {
        test.printThread(2);
    }
}

public class SynchroTest {

    public static void main(String[] args)
    {

        PrintTest p = new PrintTest();

        // passing the same object of class PrintTest to
        // both threads
        Thread1 t1 = new Thread1(p);
        Thread2 t2 = new Thread2(p);

        // start function will execute the threads
        t1.start();
        t2.start();
    }
}***
```

*****输出:*****

***<video class="wp-video-shortcode" id="video-665021-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210825114009/Java-Program-Illustrating-Lock-the-Object-for-the-shared-resource-giving-consistent-Output.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210825114009/Java-Program-Illustrating-Lock-the-Object-for-the-shared-resource-giving-consistent-Output.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210825114009/Java-Program-Illustrating-Lock-the-Object-for-the-shared-resource-giving-consistent-Output.mp4)</video>***

*****B .同步块*****

***如果我们声明一个块是同步的，那么只有写在那个块里面的代码是按顺序执行的，而不是完整的代码。当我们想要对代码的某个部分进行顺序访问或同步代码的某个部分时，就会用到它。***

*****语法:*****

```java
***synchronized (object reference) 
{    
   // Insert code here
}***
```

*****例*****

## ***Java 语言(一种计算机语言，尤用于创建网站)***

```java
***// Java Program Illustrating  Synchronized Code
// Using synchronized block

// Class 1
// Helper class extending Thread class
class PrintTest extends Thread {

    // Method  1
    // To print the thread
    public void printThread(int n)
    {

        // Making synchronized block that makes the block
        // synchronized
        synchronized (this)
        {

            // Iterating using for loop
            for (int i = 1; i <= 10; i++) {

                // Print message when these thread are
                // executing
                System.out.println("Thread " + n
                                   + " is working...");

                // Try block to check for exceptions
                try {

                    // Making thread to pause for 0.6
                    // seconds
                    Thread.sleep(600);
                }

                // Catch block to handle exceptions
                catch (Exception ex) {

                    // Print message when exception.s occur
                    System.out.println(ex.toString());
                }
            }
        }

        // Display message only
        System.out.println("--------------------------");

        try {

            // Making thread t osleep for 1 sec
            Thread.sleep(1000);
        }

        catch (Exception ex) {

            System.out.println(ex.toString());
        }
    }
}

// Class 2
// Helper class extending Thread class
class Thread1 extends Thread {

    PrintTest test;
    Thread1(PrintTest p) { test = p; }

    public void run() { test.printThread(1); }
}

// Class 3
// Helper class extending Thread class
class Thread2 extends Thread {

    PrintTest test;
    Thread2(PrintTest p) { test = p; }

    public void run() { test.printThread(2); }
}

// Class 4
// Main class
class SynchroTest {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating instance for class 1 inside main()
        PrintTest p = new PrintTest();

        // Creating threads and
        // passing same object
        Thread1 t1 = new Thread1(p);
        Thread2 t2 = new Thread2(p);

        // Starting these thread using start() method
        t1.start();
        t2.start();
    }
}***
```

*****输出:*****

***<video class="wp-video-shortcode" id="video-665021-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210826174236/syn3.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20210826174236/syn3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210826174236/syn3.mp4)</video>***

*****C .静态同步*****

***在这种情况下，同步方法被声明为**“静态”**，这意味着锁或监视器被应用于类而不是对象，因此一次只有一个线程访问该类。***

*****例*****

## ***Java 语言(一种计算机语言，尤用于创建网站)***

```java
***// Java Program Illustrate  Synchronized
// Using static synchronization

// Class 1
// Helper class
class PrintTest extends Thread {

    // Static synchronization locks the class PrintTest
    synchronized public static void printThread(int n)
    {

        for (int i = 1; i <= 10; i++) {

            // Print message when threads are executing
            System.out.println("Thread " + n
                               + " is working...");

            // Try block to check for exceptions
            try {

                // making thread to sleep for 0.6 seconds
                Thread.sleep(600);
            }

            // Catch block to handle the exceptions
            catch (Exception ex) {

                // Print message when exception occurs
                System.out.println(ex.toString());
            }
        }

        // Display message for better readobility
        System.out.println("--------------------------");

        try {
            Thread.sleep(1000);
        }

        catch (Exception ex) {
            System.out.println(ex.toString());
        }
    }
}

// Class 2
// Helper class extending Thread class
class Thread1 extends Thread {

    // run() method for thread
    public void run()
    {

        // Passing the class not the object
        PrintTest.printThread(1);
    }
}

// Class 3
// Helper class extending Thread class
class Thread2 extends Thread {

    public void run()
    {

        // Passing the class not the object
        PrintTest.printThread(2);
    }
}

// Class 4
// Main class
class SynchroTest {

    // Main driver method
    public static void main(String[] args)
    {

        // No shared object
        // Creating objects of class 2 and 3 that
        // are extending to Thr3ead class
        Thread1 t1 = new Thread1();
        Thread2 t2 = new Thread2();

        // Starting thread with help of start() method
        t1.start();
        t2.start();
    }
}***
```

*****输出:*****

***<video class="wp-video-shortcode" id="video-665021-4" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210826182606/synch.mp4?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/20210826182606/synch.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210826182606/synch.mp4)</video>***