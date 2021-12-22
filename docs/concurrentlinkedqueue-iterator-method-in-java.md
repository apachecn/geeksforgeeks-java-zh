# Java 中的 ConcurrentLinkedQueue 迭代器()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-iterator-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-iterator-method-in-java/)

**ConcurrentLinkedQueue** 的**迭代器()**方法用于以适当的顺序返回与这个 ConcurrentLinkedQueue 相同元素的迭代器。从这个方法返回的元素包含从第一个(头)到最后一个(尾)的元素。返回的迭代器弱一致。

**语法:**

```java
public Iterator iterator()
```

**返回:**该方法返回**迭代器**，其元素与 ConcurrentLinkedQueue 中的元素以正确的顺序出现。

下面的程序说明了 ConcurrentLinkedQueue 的迭代器()方法:

**例 1:**

```java
// Java Program Demonstrate iterator()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String>
            queue = new ConcurrentLinkedQueue<String>();

        // Add String to queue
        queue.add("Aman");
        queue.add("Amar");
        queue.add("Sanjeet");
        queue.add("Rabi");

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue :\n" + queue);

        // Call iterator() method
        Iterator iterator = queue.iterator();

        // Print elements of iterator
        System.out.println("\nThe String Values of iterator are:");
        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue :
[Aman, Amar, Sanjeet, Rabi]

The String Values of iterator are:
Aman
Amar
Sanjeet
Rabi

```

**例 2:**

```java
// Java Program Demonstrate iterator()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer>
            queue = new ConcurrentLinkedQueue<Integer>();

        // Add Numbers to queue
        queue.add(4353);
        queue.add(7824);
        queue.add(78249);
        queue.add(8724);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);

        // Call iterator() method
        Iterator values = queue.iterator();

        // Print elements of iterator
        System.out.println("\nThe Numbers of iterator are:");
        while (values.hasNext()) {
            System.out.println(values.next());
        }
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [4353, 7824, 78249, 8724]

The Numbers of iterator are:
4353
7824
78249
8724

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html #迭代器–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#iterator--)