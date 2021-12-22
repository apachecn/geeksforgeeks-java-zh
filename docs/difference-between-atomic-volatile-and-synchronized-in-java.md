# Java 中原子、易失和同步的区别

> 原文:[https://www . geeksforgeeks . org/原子-易失-和-同步-在 java 中的区别/](https://www.geeksforgeeks.org/difference-between-atomic-volatile-and-synchronized-in-java/)

Synchronized 是仅适用于方法和块的修饰符，但不适用于变量和类。可能会出现数据不一致的问题为了克服这个问题，当多个线程试图同时对同一个 java 对象进行操作时，我们应该使用 synchronized 关键字。如果一个方法或块声明为已同步，那么每次只允许一个线程在给定的对象上执行该方法或块，这样数据不一致的问题就会得到解决。同步关键字的主要优点是我们可以解决数据不一致的问题，但这个关键字的主要缺点是它增加了线程的等待时间，并产生了性能问题。因此，当没有具体要求时，不建议使用 synchronized 关键字。java 中的每个对象都有一个唯一的锁。当我们使用一个同步的关键字时，锁的概念就会出现。

当线程在给定对象上执行同步方法时，不允许其余线程在同一对象上同时执行任何同步方法。但是允许剩余的线程同时执行非同步方法。

**挥发性改性剂:**

如果一个变量的值不断被多个线程改变，那么就有可能出现数据不一致的问题。这是一个只适用于变量的修饰语，我们不能在其他地方应用它。我们可以通过使用 volatile 修饰符来解决这个问题。如果一个变量被声明为对于每个线程都是易变的 [**JVM**](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 将创建一个单独的本地副本。线程执行的每一次修改都将发生在本地副本中，因此对其余线程没有影响。克服数据不一致问题是优点，volatile 关键字是为每个线程创建和维护一个单独的副本，这会增加编程的复杂性，并产生性能问题，这是缺点。因此，如果没有具体的要求，绝不建议使用不稳定的关键字。

**原子修饰剂:**

如果一个变量的值不断被多个线程改变，那么就有可能出现数据不一致的问题。我们可以通过使用原子变量来解决这个问题。当这些类的对象分别表示 int、long、boolean 和 object reference 的原子变量时，可以解决数据不一致的问题。

**示例:**

在下面的例子中，每个线程将计数变量增加 5 倍。所以在执行两个线程之后，完成计数值应该是 10。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// import required packages
import java.io.*;
import java.util.*;

// creating a thread by extending a thread class
class myThread extends Thread {

    // declaring a count variable
    private int count;

    public void run()
    {
        // calculating the count
        for (int i = 1; i <= 5; i++) {

            try {
                Thread.sleep(i * 100);
                count++;
            }
            catch (InterruptedException
                       e) { // throwing an exception
                System.out.println(e);
            }
        }
    }
    // returning the count value
    public int getCount() { return this.count; }
}
// driver class
public class GFG {

    // main method
    public static void main(String[] args)
        throws InterruptedException
    {

        // creating an thread object
        myThread t = new myThread();
        Thread t1 = new Thread(t, "t1");

        // starting thread t1
        t1.start();
        Thread t2 = new Thread(t, "t2");

        // starting thread t2
        t2.start();

        // calling join method on thread t1
        t1.join();

        // calling join method on thread t1
        t2.join();

        // displaying the count
        System.out.println("count=" + t.getCount());
    }
}
```

**Output**

```
count=10
```

如果我们运行上面的程序，我们会注意到计数值在 6，7，8.9 之间变化，原因是 count++不是原子操作。因此，当一个线程读取它的值并将其递增 1 时，另一个线程已经读取了旧的值，从而导致错误的结果。为了解决这个问题，我们必须确保计数的增量操作是原子的。

下面的程序将总是输出计数值为 8，因为 AtomicInteger 方法 incrementAndGet()会自动将当前值递增 1。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// import required packages
import java.io.*;
import java.util.*;
import java.util.concurrent.atomic.AtomicInteger;

// creating a thread by extending a thread class
class myThread extends Thread {

    // declaring an atomic variable
    private AtomicInteger count = new AtomicInteger();

    public void run()
    {
        // calculating the count
        for (int i = 1; i <= 5; i++) {
            try {

                // putting  thread on sleep
                Thread.sleep(i * 100);

                // calling incrementAndGet() method
                // on count variable
                count.incrementAndGet();
            }
            catch (InterruptedException e) {

                // throwing exception
                System.out.println(e);
            }
        }
    }
    // returning the count value
    public AtomicInteger getCount() { return count; }
}
// driver class
public class GFG {

    // main method
    public static void main(String[] args)
        throws InterruptedException
    {
        // creating an thread object
        myThread t = new myThread();

        Thread t1 = new Thread(t, "t1");

        // starting thread t1
        t1.start();

        Thread t2 = new Thread(t, "t2");

        // starting thread t2
        t2.start();

        // calling join method on thread t1
        t1.join();

        // calling join method on thread t1
        t2.join();

        // displaying the count
        System.out.println("count=" + t.getCount());
    }
}
```

**Output**

```
count=10
```

<figure class="table">

| 同步的 | 不稳定的 | 原子的 |
| --- | --- | --- |
| 1.它仅适用于块或方法。 | 1.它仅适用于变量。 | 1.它也只适用于变量。 |
| 2.Synchronized 修饰符用于实现一个基于锁的并发算法，即它受到锁的限制。 | 2.而 Volatile 则提供了实现更具可扩展性的非阻塞算法的能力。 | 2.Atomic 还提供了实现非阻塞算法的能力。 |
| 3.由于锁的获取和释放，与易失性关键字和原子关键字相比，性能相对较低。 | 3.与同步关键字相比，性能相对较高。 | 3.与 volatile 和 synchronized 关键字相比，性能相对较高。 |
| 4.由于它的锁定特性，它不能避免并发危险，如死锁和活锁。 | 4.由于其非锁定性质，它不受并发危险(如死锁和活锁)的影响。 | 4.由于其非锁定性质，它不受并发危险(如死锁和活锁)的影响。 |

</figure>