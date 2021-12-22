# Java 中的 LinkedTransferQueue 迭代器()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-iterator-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-iterator-method-in-java/)

**的**迭代器()**方法是 java 中的一个内置函数，用于以适当的顺序返回这个队列中元素的迭代器。**

**语法:**

```java
LinkedTransferQueue.iterator()
```

**返回值:**该函数以适当的顺序在该队列中的元素上返回一个**迭代器**。

下面的程序说明了 LinkedTransferQueue.iterator()方法:

**程序 1:**

```java
// Java Program Demonstrate iterator()
// method of LinkedTransferQueue */

import java.util.Iterator;
import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueIteratorExample1 {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<String>
            queue = new LinkedTransferQueue<String>();

        // Adding elements to this queue
        queue.add("Gfg");
        queue.add("is");
        queue.add("fun!!");

        // Returns an iterator over the elements
        Iterator<String> iterator = queue.iterator();

        // Printing the elements of the queue
        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");
    }
}
```

**Output:**

```java
Gfg is fun!!

```

**程序 2:**

```java
// Java Program Demonstrate iterator()
// method of LinkedTransferQueue */

import java.util.Iterator;
import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueIteratorExample2 {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        queue.add(10);
        queue.add(15);
        queue.add(20);
        queue.add(25);

        // Returns an iterator over the elements
        Iterator<Integer> iterator = queue.iterator();

        // Printing the elements of the queue
        System.out.print("The queue contains ");
        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");
    }
}
```

**Output:**

```java
The queue contains 10 15 20 25

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # iterator()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#iterator())