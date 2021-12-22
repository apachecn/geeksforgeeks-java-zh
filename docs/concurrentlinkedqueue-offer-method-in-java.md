# Java 中的 ConcurrentLinkedQueue offer()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-offer-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-offer-method-in-java/)

**ConcurrentLinkedQueue** 的 **offer()** 方法用于在这个 ConcurrentLinkedQueue 的尾部插入作为参数传递的元素。如果插入成功，此方法返回真。ConcurrentLinkedQueue 是无界的，所以这个方法 offer()永远不会返回 false。

**语法:**

```java
public boolean offer(E e)
```

**参数:**这个方法采用单个参数 **e** ，它代表我们想要插入到这个 ConcurrentLinkedQueue 中的元素。

**返回:**该方法在成功插入元素后返回**真**。

**异常:**如果指定的元素为空，该方法抛出**空指针异常**。

以下程序说明了并发链接队列的 offer()方法:

**例 1:** 演示 ConcurrentLinkedQueue 添加字符串的 offer()方法。

```java
// Java Program Demonstrate offer()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String>
            queue = new ConcurrentLinkedQueue<String>();

        // Add String to queue using offer() method
        queue.offer("Aman");
        queue.offer("Amar");
        queue.offer("Sanjeet");
        queue.offer("Rabi");

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [Aman, Amar, Sanjeet, Rabi]

```

**例 2:** 演示用于添加数字的 ConcurrentLinkedQueue 的 offer()方法。

```java
// Java Program Demonstrate offer()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer>
            queue = new ConcurrentLinkedQueue<Integer>();

        // Add Numbers to queue using offer
        queue.offer(4353);
        queue.offer(7824);
        queue.offer(78249);
        queue.offer(8724);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [4353, 7824, 78249, 8724]

```

**示例 3:** 演示 offer()方法抛出的 NullPointerException 用于添加 Null。

```java
// Java Program Demonstrate offer()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer>
            queue = new ConcurrentLinkedQueue<Integer>();

        // Add null to queue
        try {
            queue.offer(null);
        }
        catch (NullPointerException e) {
            System.out.println("Exception thrown"
                               + " while adding null: " + e);
        }
    }
}
```

**输出:**

```java
Exception thrown while adding null: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html # offer-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#offer-E-)