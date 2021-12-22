# Java 中 LinkedTransferQueue put()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-put-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-put-method-in-java/)

**java . util . concurrent . linkedtransferqueue . put()**方法是 Java 中的一个内置函数，用于在这个队列中插入一个元素。如果队列已满，它会一直等到空间可用。

**语法:**

```java
LinkedTransferQueue.put(E e)
```

**参数:**该函数接受单个参数 *e* ，即要插入的元素。

**返回值:**函数不返回任何内容。

**异常:**当指定元素为空时，函数显示空指针异常。

下面的程序说明了 LinkedTransferQueue.put()方法:

**程序 1:** 在队列中插入整数。

```java
/* Java Program Demonstrate put()
method of LinkedTransferQueue */

import java.util.concurrent.*;

class LinkedTransferQueuePutExample1 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<Integer> queue = 
                 new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 10; i <= 15; i++)
            queue.put(i);

        // Printing the elements of the queue
        System.out.println("The elements in the queue are:");
        for (Integer i : queue)
            System.out.print(i + " ");
    }
}
```

**输出:**

```java
The elements in the queue are:
10 11 12 13 14 15

```

**程序 2:** 在队列中添加字符串。

```java
/* Java Program Demonstrate put()
method of LinkedTransferQueue */

import java.util.concurrent.*;

class LinkedTransferQueuePutExample2 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<String> queue = 
                     new LinkedTransferQueue<String>();

        // Adding elements to this queue
        queue.put("alex");
        queue.put("bob");
        queue.put("chuck");
        queue.put("drake");
        queue.put("erick");

        // Printing the elements of the queue
        System.out.println("The elements in the queue are:");
        for (String i : queue)
            System.out.print(i + " ");
    }
}
```

**输出:**

```java
The elements in the queue are:
alex bob chuck drake erick

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # put(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#put(E))