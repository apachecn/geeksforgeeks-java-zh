# Java 中的 LinkedTransferQueue isEmpty()方法

> 原文:[https://www . geeksforgeeks . org/linkedtransferqueue-isempty-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-isempty-method-in-java/)

**java . util . concurrent . linkedtransferqueue**的 **isEmpty()** 方法是 Java 中的一个内置函数，它检查这个队列是否为空。

**语法:**

```java
LinkedTransferQueue.isEmpty()
```

**返回值:**该函数返回一个**布尔值**。如果 LinkedTransferQueue 为空，则返回 true，否则返回 false。

下面的程序说明了 LinkedTransferQueue.isEmpty()方法:

**程序 1:** 在该程序中，链接传输队列是非空的。

```java
// Java Program Demonstrate isEmpty()
// method of LinkedTransferQueue

import java.util.concurrent.*;

class LinkedTransferQueueIsEmptyExample1 {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 10; i <= 15; i++)
            queue.add(i);

        // Checks if this queue is empty or not
        if (queue.isEmpty())
            System.out.println("The queue is empty.");
        else
            System.out.println("The queue is non-empty.");
    }
}
```

**输出:**

```java
The queue is non-empty.

```

**程序 2:** 在该程序中，链接传输队列为空。

```java
// Java Program Demonstrate isEmpty()
// method of LinkedTransferQueue */

import java.util.concurrent.*;

class LinkedTransferQueueIsEmptyExample2 {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // Checks if this queue is empty or not
        if (queue.isEmpty())
            System.out.println("The queue is empty.");
        else
            System.out.println("The queue is non-empty.");
    }
}
```

**输出:**

```java
The queue is empty.

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # isEmpty()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#isEmpty())