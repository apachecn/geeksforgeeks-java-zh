# Java 中的 ConcurrentLinkedQueue peek()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-peek-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-peek-method-in-java/)

**ConcurrentLinkedQueue** 的 **peek()** 方法用于返回 ConcurrentLinkedQueue 的头。它检索但不移除这个 ConcurrentLinkedQueue 的头。如果 ConcurrentLinkedQueue 为空，则此方法返回 null。

**语法:**

```
public E peek()
```

**返回:**这个方法返回这个 ConcurrentLinkedQueue 的**头**而不删除它。

下面的程序说明了并发链接队列的 peek()方法:

**例 1:**

```
// Java Program Demonstrate peek()
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

        // find peek
        int response1 = queue.peek();

        // print after applying peek method
        System.out.println("Head: " + response1);

        // Verifying that the head is not removed
        System.out.println("ConcurrentLinkedQueue after peek: " + queue);
    }
}
```

**输出:**

```
ConcurrentLinkedQueue: [4353, 7824, 78249, 8724]
Head: 4353
ConcurrentLinkedQueue after peek: [4353, 7824, 78249, 8724]

```

**例 2:**

```
// Java Program Demonstrate peek()
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

        // find peek of queue
        String response1 = queue.peek();

        // print after applying peek method
        System.out.println("Head: " + response1);

        // Verifying that the head is not removed
        System.out.println("ConcurrentLinkedQueue after peek: " + queue);

        // remove some elements
        queue.poll();
        queue.poll();

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("Updated ConcurrentLinkedQueue: " + queue);

        // find peek of queue
        String response2 = queue.peek();

        // print after applying peek method
        System.out.println("Head: " + response1);

        // Verifying that the head is not removed
        System.out.println("ConcurrentLinkedQueue after peek: " + queue);
    }
}
```

**输出:**

```
ConcurrentLinkedQueue: [Aman, Amar, Sanjeet, Rabi]

Head: Aman

ConcurrentLinkedQueue after peek: [Aman, Amar, Sanjeet, Rabi]

Updated ConcurrentLinkedQueue: [Sanjeet, Rabi]

Head: Aman

ConcurrentLinkedQueue after peek: [Sanjeet, Rabi]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html # peek–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#peek--)