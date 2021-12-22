# Java 中无锁算法的 AtomicInteger】

> 原文:[https://www . geeksforgeeks . org/atomicintger-for-lock-free-algorithms-in-Java/](https://www.geeksforgeeks.org/atomicinteger-for-lock-free-algorithms-in-java/)

**无锁算法**是一种机制，在这种机制中，无需使用像互斥体这样的同步原语，就可以对共享数据进行线程安全访问。多线程应用程序具有共享资源，这些资源可以在应用程序中使用的不同线程之间传递。

*   这造成了线程间竞争条件和数据竞争的威胁。为了处理这种情况，使用了各种技术。最常见的方法之一是使用同步和锁(也称为监视器)，这可以确保线程安全。然而，如果使用过多的同步，随着应用程序变得越来越复杂，应用程序的性能将受到巨大影响。

*   我们需要编写线程安全的应用程序，但同时，它们应该给我们带来高性能和并发执行的好处。因此，为了最大限度地减少同步的使用并降低锁的复杂性，Java 在 java.util .并发包中有一整套类，它提供了许多无锁和原子的高级操作。

*   应用程序中的大量操作可以在不需要同步大部分代码的情况下执行。我们需要了解什么在某种情况下最适用，并为工作使用正确的工具。

*   我们将看到一个例子，首先我们展示如何在多线程应用程序中使用同步锁定来实现并发，然后我们将看到一个解决方案，为同一问题提供无锁解决方案。

以下示例显示了同步和锁定机制是如何用作并发解决方案的。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate the 
// Synchronization of threads
// using Locks 

import java.io.*;

class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {
        // Creating Obj for CountTrees Class 
        CountTrees countTrees = new CountTrees();

        // Creating Obj for IncreaseTrees Class 
        IncreaseTrees increaseTreesThread = new IncreaseTrees(countTrees);

        // Creating Obj for IncreaseConcrete Class
        IncreaseConcrete increaseConcreteThread
            = new IncreaseConcrete(countTrees);

        // Starting both Thread increaseTreesThread 
        // And increaseConcreteThread by using start method. 
        increaseTreesThread.start();
        increaseConcreteThread.start();

        // Join method Enable threads wait to complete 
        increaseTreesThread.join();
        increaseConcreteThread.join();

        // To print the no. of trees by getting current 
        // value by using countTrees Obj. 
        System.out.println("Number of trees in your area ::"
                           + countTrees.getNumOfTrees());
    }
}

// Implementation of IncreaseTrees using Thread
class IncreaseTrees extends Thread {

    private CountTrees countTrees;

    IncreaseTrees(CountTrees countTrees)
    {
        this.countTrees = countTrees;
    }

    @Override
    public void run()
    {
        System.out.println("Planting trees in progress...");
        countTrees.plantTrees();
    }
}

// Implementation of IncreaseConcrete using Thread
class IncreaseConcrete extends Thread {

    private CountTrees countTrees;

    IncreaseConcrete(CountTrees countTrees)
    {
        this.countTrees = countTrees;
    }

    @Override
    public void run()
    {
        System.out.println("Concretization in progress...");
        countTrees.concretizing();
    }
}

// Synchronizing the shared resources
class CountTrees {

    private int trees = 10000;

    public synchronized void plantTrees()
    {
        for (int i = 0; i < 10000; i++)
            trees++;
    }

    public synchronized void concretizing()
    {
        for (int i = 0; i < 10000; i++)
            trees--;
    }

    public synchronized int getNumOfTrees()
    {
        return this.trees;
    }
}
```

**输出:**

```java
Planting trees in progress...
Concretization in progress...
Number of trees in your area:: 10000

```

现在，为了将上面的例子转换成一个简单的无锁示例，我们使用了 Java 的**原子集成器**类，它是并发包**的一部分。这是一个非常有用的类，可以很容易地在并发应用程序中使用，如下所示:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate to achieve concurrency
// with the help of AtomicInteger class which is used
// in application like atomically incremented the counter

// Lock Free program for achieving concurrency
import java.io.*;

// Java provides wrapper class to achieve atomic 
// operations without the use of synchronization 
// like java.util.concurrent.atomic.AtomicInteger
import java.util.concurrent.atomic.AtomicInteger;

class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // Creating Obj for CountTrees Class
        CountTrees countTrees = new CountTrees();

        // Creating Obj for IncreaseTrees Class
        IncreaseTrees increaseTreesThread
            = new IncreaseTrees(countTrees);

        // Creating Obj for IncreaseConcrete Class
        IncreaseConcrete increaseConcreteThread
            = new IncreaseConcrete(countTrees);

        // Starting both Thread increaseTreesThread
        // and increaseConcreteThread by using 
        // start method.
        increaseTreesThread.start();
        increaseConcreteThread.start();

        // join method Enable threads wait to complete
        increaseTreesThread.join();
        increaseConcreteThread.join();

        // To print the no. of trees by getting current
        // value by using countTrees Obj.
        System.out.println("Number of trees in your area ::"
                           + countTrees.getNumOfTrees());
    }
}

// Implementation of IncreaseTrees class
class IncreaseTrees extends Thread {

    private CountTrees countTrees;

    IncreaseTrees(CountTrees countTrees)
    {
        this.countTrees = countTrees;
    }

    @Override public void run()
    {
        System.out.println("Planting trees in process...");
        countTrees.plantTrees();
    }
}

class IncreaseConcrete extends Thread {

    private CountTrees countTrees;

    IncreaseConcrete(CountTrees countTrees)
    {
        this.countTrees = countTrees;
    }

    @Override public void run()
    {
        System.out.println("Concretization in progress...");
        countTrees.concretizing();
    }
}

// Implementation of CountTrees Class
class CountTrees {

    // In java AtomicInteger Class provides operations on
    // underlying int value that can be read and 
    // written atomically.
    private AtomicInteger trees = new AtomicInteger(10000);

    // Implementation of plantTrees method
    public void plantTrees()
    {
        // AtomicInteger class obj trees
        // atomically incremented the value.
        for (int i = 0; i < 10000; i++)
            trees.incrementAndGet();
    }
    // Implementation of concretizing method
    public void concretizing()
    {
        // AtomicInteger class obj trees
        // decremented the value.
        for (int i = 0; i < 10000; i++)
            trees.decrementAndGet();
    }

    public int getNumOfTrees()
    {
        // AtomicInteger class obj
        // trees Gets the current
        // value.
        return trees.get();
    }
}
```

**输出:**

```java
Concretization in progress...
Planting trees in process...
Number of trees in your area::10000

```

**总结和要点:**

*   *AtomicInteger* 类是一个很好的工具，可以用在简单的应用程序中，比如并发计数和构建简单可读的代码，而不需要使用锁的复杂性。
*   *AtomicInteger* 应该只在需要原子操作的时候使用。此外，竞争条件仍然可以存在于两个独立的原子操作之间。
*   *AtomicInteger* 类是不相上下的，有时可能比使用锁作为保护的常规整数更有效。
*   如果应用程序只使用一个线程，则首选常规整数。

**参考文献:**Java 中的 [AtomicInteger 类](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#AtomicIntege)