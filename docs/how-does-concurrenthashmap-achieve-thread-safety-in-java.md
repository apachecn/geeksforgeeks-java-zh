# 在 Java 中，ConcurrentHashMap 是如何实现线程安全的？

> 原文:[https://www . geesforgeks . org/how-do-concurrenthashmap-reach-thread-safety-in-Java/](https://www.geeksforgeeks.org/how-does-concurrenthashmap-achieve-thread-safety-in-java/)

[**ConcurrentHashMap**](https://www.geeksforgeeks.org/concurrenthashmap-in-java/)是一个哈希表，支持完全并发的检索和高预期并发的更新。这个类遵循与哈希表相同的功能规范，并且包括哈希表的所有方法。ConcurrentHashMap 在 java.util.Concurrent 包中。

**语法:**

```java
public class ConcurrentHashMap<K,V>
extends AbstractMap<K,V>
implements ConcurrentMap<K,V>, Serializable
```

其中 K 表示该映射维护的键的类型，V 表示映射值的类型

**并发哈希映射的需求:**

*   虽然 HashMap 有很多优点，但它不能用于多线程，因为它不是线程安全的。
*   尽管哈希表被认为是线程安全的，但它也有一些缺点。例如，哈希表需要锁才能打开，即使它不影响对象。
*   n HashMap，如果一个线程正在迭代一个对象，另一个线程试图访问同一个对象，它会抛出 ConcurrentModificationException，而 concurrent hashmap 不会抛出 ConcurrentModificationException。

**如何使 ConcurrentHashMap 成为线程安全的？**

*   Java . util . concurrenthashmap 类通过将映射划分为多个段来实现线程安全，锁不是针对整个对象，而是针对一个段，即一个线程需要一个段的锁。
*   在并发事务中，读取操作不需要任何锁。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to llustarte ConcurrentModificationException
// Using Normal Collections

// Importing required classes
import java.util.*;
import java.util.concurrent.*;

// Main class extending Thread class
class GFG extends Thread {

    // Creating a static HashMap class object
    static HashMap m = new HashMap();

    // run() method for the thread
    public void run()
    {

        // Try block to check for exceptions
        try {

            // Making thread to sleep for 3 seconds
            Thread.sleep(2000);
        }

        // Catch block to handle exceptions
        catch (InterruptedException e) {
        }

        // Display message
        System.out.println("Child Thread updating Map");

        // Putting element in map
        m.put(103, "C");
    }

    // Method 2
    // Main driver method
    public static void main(String arg[])
        throws InterruptedException
    {

        // Adding elements to map object created above
        // using put() method
        m.put(101, "A");
        m.put(102, "B");

        // Creating thread inside main() method
        GFG t = new GFG();

        // Starting the thread
        t.start();

        // Operating keySet() method and
        // storing it in Set class object
        Set s1 = m.keySet();

        // Iterating over Set class object
        // using iterators
        Iterator itr = s1.iterator();

        // Holds true till there is single element present
        // inside object
        while (itr.hasNext()) {

            // traversign over elements in object
            // using next() method
            Integer I1 = (Integer)itr.next();

            // Print statement
            System.out.println(
                "Main Thread Iterating Map and Current Entry is:"
                + I1 + "..." + m.get(I1));

            // Making thread to sleep for 3 seconds
            Thread.sleep(3000);
        }

        // Printing all elements on console
        System.out.println(m);
    }
}
```

**输出:**

```java
Main Thread Iterating Map and Current Entry is:101...A
Child Thread updating Map
Exception in thread "main" java.util.ConcurrentModificationException
       at java.base/java.util.HashMap$HashIterator.nextNode(HashMap.java:1493)
       at java.base/java.util.HashMap$KeyIterator.next(HashMap.java:1516)
       at Main.main(Main.java:30)
```

**输出解释:**

上述程序中使用的类扩展了 Thread 类。让我们看看控制流。所以，最初，上面的 java 程序包含一个线程。当我们遇到语句 Main t= new Main()时，我们正在为一个扩展 Thread 类的类创建一个对象。现在主线程开始执行，每当子线程更新同一个映射对象时，它都会抛出一个名为 ConcurrentModificationException 的异常。

现在让我们通过使用 ConcurrentHashMap 来修改上述程序，以便解决在执行上述程序时生成的上述异常。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to llustarte ConcurrentModificationException
// Using ConcurrentHashMap

// Importing required classes
import java.util.*;
import java.util.concurrent.*;

// Main class extending Thread class
class Main extends Thread {

    // Creating static concurrentHashMap object
    static ConcurrentHashMap<Integer, String> m
        = new ConcurrentHashMap<Integer, String>();

    // Method 1
    // run() method for the thread
    public void run()
    {

        // Try block to check for exceptions
        try {

            // Making thread to sleep for 2 seconds
            Thread.sleep(2000);
        }

        // Catch block to handle the exceptions
        catch (InterruptedException e) {
        }

        // Display message
        System.out.println("Child Thread updating Map");

        // Inserting element
        m.put(103, "C");
    }

    // Method 2
    // Main driver method
    public static void main(String arg[])
        throws InterruptedException
    {

        // Adding elements to object created of Map
        m.put(101, "A");
        m.put(102, "B");

        // Creating thread inside main() method
        Main t = new Main();

        // Starting thread
        t.start();

        // Creating object of Set class
        Set<Integer> s1 = m.keySet();

        // Creating iterator for traversal
        Iterator<Integer> itr = s1.iterator();

        // Condition holds true till there is single element
        // in Set object
        while (itr.hasNext()) {

            // Iterating over elements
            // using next() method
            Integer I1 = itr.next();

            // Display message
            System.out.println(
                "Main Thread Iterating Map and Current Entry is:"
                + I1 + "..." + m.get(I1));

            // Making thread to sleep for 3 seconds
            Thread.sleep(3000);
        }

        // Display elements of map objects
        System.out.println(m);
    }
}
```

**Output**

```java
Main Thread Iterating Map and Current Entry is:101...A
Child Thread updating Map
Main Thread Iterating Map and Current Entry is:102...B
Main Thread Iterating Map and Current Entry is:103...C
{101=A, 102=B, 103=C}
```

**输出解释:**

上述程序中使用的类扩展了[线程类。](https://www.geeksforgeeks.org/java-lang-thread-class-java/)让我们看看控制流，因为我们知道在 ConcurrentHashMap 中，当一个线程迭代时，剩余的线程可以以安全的方式执行任何修改。在上面的程序中，主线程正在更新地图，同时子线程也在尝试更新地图对象。这个程序不会抛出 ConcurrentModificationException。

### 【Hashtable、Hashmap、ConcurrentHashmap 之间的区别

<figure class="table">

| 

散列表

 | 

HashMap

 | 

ConcurrentHashMap

 |
| --- | --- | --- |
| 我们将通过锁定整个地图对象来获得线程安全。 | 它不是线程安全的。 | 我们将获得线程安全，而不需要仅仅用段级锁定来锁定全图对象。 |
| 每个读写操作都需要一个 objectstotal 映射对象锁。 | 它不需要锁。 | 读操作可以在没有锁定的情况下执行，但写操作可以在段级锁定的情况下执行。 |
| 一次只允许一个线程在 map 上操作(同步) | 一次不允许多个线程运行。它将引发异常 | 一次允许多个线程以安全的方式对地图对象进行操作 |
| 当一个线程迭代映射对象时，其他线程不允许修改映射，否则我们会得到 ConcurrentModificationException | 当一个线程迭代映射对象时，其他线程不允许修改映射，否则我们会得到 ConcurrentModificationException | 当一个线程迭代映射对象时，其他线程可以修改映射，我们不会得到 ConcurrentModificationException |
| 键和值都不允许为 Null | HashMap 允许一个空键和多个空值 | 键和值都不允许为 Null。 |
| 在 1.0 版本中引入 | 在 1.2 版本中引入 | 在 1.5 版本中引入 |

</figure>