# Java 中使用静态修饰符的类加载和静态块执行

> 原文:[https://www . geesforgeks . org/class-loading-static-blocks-execution-use-static-修饰符-in-java/](https://www.geeksforgeeks.org/class-loading-and-static-blocks-execution-using-static-modifier-in-java/)

Static 是一个关键字，当它被附加到方法、变量、块时，就成为类方法、类变量和类块。您可以使用类名调用静态变量/方法。 [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 在“**类加载时间”**执行静态块

**执行顺序:**

静态块/方法/变量的初始化是有顺序的。

静态块甚至在主方法之前就被调用了，主方法只不过是一个静态方法，即每个类的执行点。

**注:**

> 有时在面试中被要求打印“HELLO”，不在 main 方法内部打印，也不从 main 调用任何方法。答案是使用静态块，因为它们是在 main 之前初始化的，所以您可以使用它们来打印任何东西，而不依赖于 java 中的 main Method。

## Java

```java
// Class Loading and Static Blocks
// Execution Using Static Modifier in Java

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Created 3 Threads
        MyThread myThread1 = new MyThread();
        myThread1.start();

        MyThread myThread2 = new MyThread();
        myThread2.start();

        MyThread myThread3 = new MyThread();
        myThread3.start();
    }
}

class MyThread extends Thread {

    // Static Variable count is maintained across
    // all threads as it is only created once
    static int count = 0;

    // Non Static Variable count is maintained separately
    // for separate thread As non-static variables are
    // created for every thread
    int notStatic = 0;
    public void run()
    {
        count++;
        notStatic++;
        System.out.println("Thread = " + count);
        System.out.println("Non Static Variable Value="
                           + notStatic);
    }
}
```

**输出**

```java
Thread = 3
Thread = 2
Non Static Variable Value=1
Thread = 1
Non Static Variable Value=1
Non Static Variable Value=1
```

**<u>静态变量</u>**

您可以使用静态变量来节省内存，或者在一个操作中，您希望所有线程都维护一个变量，而不是每个线程都有不同的变量。

**<u>静法</u>**

当方法比类的实例与类更相关时使用。java 中的数学课是 Java 中的一个很好的例子。它有所有的静态方法，你可以用一个类名比如 max，min，pow 来调用，因为这些函数不需要不同的对象有不同的值。您可以使用类名.方法名()传递参数并获得答案。

**<u>静座</u>**

<u>当您想要在执行控制转到其他方法(如 main 方法)之前初始化任何数据时使用。</u>

<u>**<u>规则:</u>**</u>

<u>*   Static methods can only call other static methods, that is, they cannot call non-static methods from static methods like main methods.*   Static blocks can directly use unique static variables.</u>

<u>单例设计模式是最广泛使用的设计模式，其中对于类的每个实例请求，只创建和返回类的一个实例。static 关键字用于只创建一次对象，因为 static 只占用一次内存，因此每次调用都会保持同步。</u>

<u>下面的例子清楚地显示了执行的顺序。静态块首先被调用，即使它写在主方法之后。它证明了静态块是在主方法之前首先被调用的东西。</u>

 <u>## 爪哇

```java
// Class Loading and Static Blocks
// Execution Using Static Modifier in Java

import java.io.*;

class GFG {

    // Static Variable
    public static void main(String[] args)
    {
        System.out.println("Static Variable=" + count);
        System.out.println("Static Method");
    }

    // Static Variable
    static int count = 3;

    // Called even before Main Method
    static { System.out.println("Static Block"); }
}
```</u> <u>**输出**

```java
Static Block
Static Variable=3
Static Method
```

**真实例子:**要将输出追加到同一个日志文件，创建一个 logger 对象，使用 logger.info()可以按照插入顺序追加数据。</u>