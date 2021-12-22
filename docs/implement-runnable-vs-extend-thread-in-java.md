# 在 Java 中实现可运行与扩展线程

> 原文:[https://www . geesforgeks . org/implement-runnable-vs-extend-thread-in-Java/](https://www.geeksforgeeks.org/implement-runnable-vs-extend-thread-in-java/)

正如在 [Java 多线程](https://www.geeksforgeeks.org/multithreading-in-java/)文章中所讨论的，我们可以通过以下两种方式定义线程:

*   通过扩展线程类
*   通过实现可运行的接口

在第一种方法中，我们的类总是扩展线程类。没有机会扩展任何其他类。因此，我们错过了继承的好处。在第二种方法中，当实现 Runnable 接口时，我们可以扩展任何其他类。因此，我们能够利用继承的好处。
由于以上原因，建议实现 Runnable 接口方式，而不是扩展 Thread 类。

**扩展 Thread 类和实现 Runnable 接口的显著区别:**

*   当我们扩展线程类时，我们甚至不能扩展我们需要的任何其他类，当我们实现 Runnable 时，我们可以为我们的类节省空间，以便将来或现在扩展任何其他类。
*   当我们扩展线程类时，我们的每个线程都创建唯一的对象并与之关联。当我们实现 Runnable 时，它将同一个对象共享给多个线程。

让我们看看下面的程序，以便更好地理解:

```java
// Java program to illustrate defining Thread
// by extending Thread class

// Here we cant extends any other class
class Test extends Thread 
{
    public void run()
    {
        System.out.println("Run method executed by child Thread");
    }
    public static void main(String[] args)
    {
        Test t = new Test();
        t.start();
        System.out.println("Main method executed by main thread");
    }
}
```

**输出:**

```java
Main method executed by main thread
Run method executed by child Thread

```

```java
// Java program to illustrate defining Thread
// by implements Runnable interface
class Geeks {
    public static void m1()
    {
        System.out.println("Hello Visitors");
    }
}

// Here we can extends any other class
class Test extends Geeks implements Runnable {
    public void run()
    {
        System.out.println("Run method executed by child Thread");
    }
    public static void main(String[] args)
    {
        Test t = new Test();
        t.m1();
        Thread t1 = new Thread(t);
        t1.start();
        System.out.println("Main method executed by main thread");
    }
}
```

**输出:**

```java
Hello Visitors
Main method executed by main thread
Run method executed by child Thread

```

**注意:**在多线程的情况下，我们无法预测输出的确切顺序，因为它会因系统或 JVM 而异。

**参考:**[https://stackoverflow . com/questions/15471432/why-implements-runnable-is-preferred-over-extensions-thread](https://stackoverflow.com/questions/15471432/why-implements-runnable-is-preferred-over-extends-thread)

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。