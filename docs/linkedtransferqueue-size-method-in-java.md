# Java 中 LinkedTransferQueue size()方法

> 原文:[https://www . geeksforgeeks . org/linkedtransferqueue-size-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-size-method-in-java/)

**java . util . concurrent . linkedtransferqueue . size()**方法是 Java 中的一个内置函数，它给出了队列中存在的元素的总数。

**语法:**

```java
LinkedTransferQueue.size()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回队列中元素的个数。

下面的程序说明了 LinkedTransferQueue.size()方法:

**程序 1:**

```java
// Java Program Demonstrate size()
// method of LinkedTransferQueue 

import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueSizeExample1 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<Integer> queue =
                      new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 1; i <= 10; i++)
            queue.add(i);

        // Printing the size of the queue
        System.out.println("Number of elements in the queue = " 
                                                + queue.size());
        // Printing the elements
        System.out.println("Queue : " + queue);
    }
}
```

**输出:**

```java
Number of elements in the queue = 10
Queue : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

```

**程序二:**

```java
// Java Program Demonstrate size()
// method of LinkedTransferQueue 

import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueSizeExample2 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<String> queue = 
                  new LinkedTransferQueue<String>();

        // Adding elements to this queue
        queue.add("A");
        queue.add("B");
        queue.add("C");
        queue.add("D");
        queue.add("E");

        // Printing the size of the queue
        System.out.println("Number of elements in the queue = " 
                                                + queue.size());
        // Printing the elements
        System.out.println("Queue : " + queue);
    }
}
```

**输出:**

```java
Number of elements in the queue = 5
Queue : [A, B, C, D, E]

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # size()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#size())