# Java 中的 ConcurrentLinkedQueue size()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-size-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-size-method-in-java/)

**ConcurrentLinkedQueue** 的 **size()** 方法用于返回该 ConcurrentLinkedQueue 包含的元素数量。

**语法:**

```java
public int size()
```

**返回:**这个方法**这个 ConcurrentLinkedQueue 中的元素数量**。

下面的程序说明了并发链接队列的大小()方法:

**例 1:**

```java
// Java Program Demonstrate size()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

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

        // apply size()
        int size = queue.size();

        // print after applying size method
        System.out.println("Size of ConcurrentLinkedQueue: " + size);
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [4353, 7824, 78249, 8724]
Size of ConcurrentLinkedQueue: 4

```

**例 2:**

```java
// Java Program Demonstrate size()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

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
        System.out.println("ConcurrentLinkedQueue: " + queue);

        // apply size() on queue
        int size = queue.size();

        // print after applying size method
        System.out.println("Size of ConcurrentLinkedQueue: "
                           + size);

        // removal of some elements
        queue.poll();
        queue.poll();

        // get size of ConcurrentLinkedQueue again
        size = queue.size();

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("After 2 removal of elements\n"
                           + "ConcurrentLinkedQueue: " + queue);

        // print after applying size method
        System.out.println("Size of ConcurrentLinkedQueue: "
                           + size);
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [Aman, Amar, Sanjeet, Rabi]
Size of ConcurrentLinkedQueue: 4

After 2 removal of elements

ConcurrentLinkedQueue: [Sanjeet, Rabi]
Size of ConcurrentLinkedQueue: 2

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html # size–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#size--)