# Java 中的 ConcurrentLinkedQueue poll()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-poll-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-poll-method-in-java/)

**ConcurrentLinkedQueue** 的 **poll()** 方法用于移除并返回该 ConcurrentLinkedQueue 的头。如果 ConcurrentLinkedQueue 为空，则此方法将返回 null。

**语法:**

```
public E poll()
```

**返回:**该方法删除并返回该并发链接队列的**头**，如果该队列为空，则返回**空**。

以下程序说明了并发链接队列的轮询()方法:

**例 1:**

```
// Java Program Demonstrate poll()
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

        // apply poll()
        int response1 = queue.poll();

        // print after applying poll method
        System.out.println("Head: " + response1);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("Current ConcurrentLinkedQueue: " + queue);
    }
}
```

**输出:**

```
ConcurrentLinkedQueue: [4353, 7824, 78249, 8724]
Head: 4353
Current ConcurrentLinkedQueue: [7824, 78249, 8724]

```

**例 2:**

```
// Java Program Demonstrate poll()
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

        // apply poll() on queue
        String response1 = queue.poll();

        // print after applying poll method
        System.out.println("Head: " + response1);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("Current ConcurrentLinkedQueue: " + queue);

        // apply poll() on queue more than one time
        queue.poll();
        queue.poll();

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("After 2 poll() applied\n"
                           + "ConcurrentLinkedQueue: " + queue);
    }
}
```

**输出:**

```
ConcurrentLinkedQueue: [Aman, Amar, Sanjeet, Rabi]
Head: Aman
Current ConcurrentLinkedQueue: [Amar, Sanjeet, Rabi]
After 2 poll() applied
ConcurrentLinkedQueue: [Rabi]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html # poll–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#poll--)