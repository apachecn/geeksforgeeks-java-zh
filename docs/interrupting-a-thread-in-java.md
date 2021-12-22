# 中断 Java 中的线程

> 原文:[https://www . geesforgeks . org/interruption-a-thread-in-Java/](https://www.geeksforgeeks.org/interrupting-a-thread-in-java/)

在 Java Threads 中，如果任何线程处于睡眠或等待状态(即调用 sleep()或 wait()，则调用线程上的 interrupt()方法，会引发中断异常，从而打破睡眠或等待状态。如果线程不处于睡眠或等待状态，调用 interrupt()方法会执行正常行为，不会中断线程，但会将中断标志设置为 true。

**interrupt()方法:**如果任何线程处于睡眠或等待状态，那么使用 interrupt()方法，我们可以通过显示 InterruptedException 来中断该线程的执行。处于睡眠或等待状态的线程可以借助 thread 类的 interrupt()方法被中断。

**示例:**假设有两个线程，如果其中一个线程在调用 Object 类的 wait()、wait(long)或 wait(long，int)方法时被阻塞，或者在调用该类的 [join()](https://www.geeksforgeeks.org/joining-threads-in-java/) 、join(long)、join(long，int)、sleep(long)或 sleep(long，int)方法时被阻塞，那么它的中断状态将被清除，并且它将接收到一个中断异常，这给了另一个线程执行另一个线程的相应 run()方法的机会，这将导致高性能并降低性能

### 我们可以中断线程的不同场景

**情况 1:中断一个没有停止工作的线程:**在程序中，我们使用 try and catch 块处理中断异常，所以每当任何线程中断当前正在执行的线程时，它都会从睡眠状态中出来，但不会停止工作。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate the
// concept of interrupt() method
// while a thread does not stops working

class MyClass extends Thread {
    public void run()
    {
        try {
            for (int i = 0; i < 5; i++) {
                System.out.println("Child Thread executing");

                // Here current threads goes to sleeping state
                // Another thread gets the chance to execute
                Thread.sleep(1000);
            }
        }
        catch (InterruptedException e) {
            System.out.println("InterruptedException occur");
        }
    }
}

class Test {
    public static void main(String[] args)
            throws InterruptedException
    {
        MyClass thread = new MyClass();
        thread.start();

        // main thread calls interrupt() method on
        // child thread
        thread.interrupt();

        System.out.println("Main thread execution completes");
    }
}
```

**Output**

```java
Main thread execution completes
Child Thread executing
InterruptedException occur
```

**情况 2:中断一个停止工作的线程:**在程序中，中断当前正在执行的线程后，我们在 catch 块中抛出一个新的异常，这样它就会停止工作。

## 爪哇

```java
// Java Program to illustrate the
// concept of interrupt() method
// while a thread stops working

class Geeks extends Thread {
    public void run()
    {
        try {
            Thread.sleep(2000);
            System.out.println("Geeksforgeeks");
        }
        catch (InterruptedException e) {
            throw new RuntimeException("Thread " +
                                    "interrupted");
        }
    }
    public static void main(String args[])
    {
        Geeks t1 = new Geeks();
        t1.start();
        try {
            t1.interrupt();
        }
        catch (Exception e) {
            System.out.println("Exception handled");
        }
    }
}
```

**输出**

```java
Exception in thread "Thread-0" java.lang.RuntimeException: Thread interrupted
    at Geeks.run(File.java:13)
```

**案例三:中断正常工作的线程:**在程序中，线程执行过程中没有出现异常。这里，interrupt 只将中断标志设置为 true，Java 程序员以后可以使用。

## Java

```java
// Java Program to illustrate the concept of
// interrupt() method

class Geeks extends Thread {
    public void run()
    {
        for (int i = 0; i < 5; i++)
            System.out.println(i);
    }
    public static void main(String args[])
    {
        Geeks t1 = new Geeks();
        t1.start();
        t1.interrupt();
    }
}
```

**输出**

```java
0
1
2
3
4
```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。