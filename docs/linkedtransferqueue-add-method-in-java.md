# Java 中 LinkedTransferQueue add()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-add-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-add-method-in-java/)

java . util . concurrent . linkedtransferqueue 的 **add()** 方法是 Java 中的一个内置函数，用来在这个队列中插入一个元素。

**语法:**

```java
LinkedTransferQueue.add(E e)
```

**参数:**该函数接受单个参数 *e* ，即要插入的元素。

**返回值:**函数返回一个布尔值。

**异常:**当指定元素为空时，函数抛出**空指针异常**。

下面的程序说明了 Java . util . concurrent . linkedtransferqueue . add()的使用:

**程序 1:** 在队列中插入整数。

```java
// Java Program Demonstrate add()
// method of LinkedTransferQueue

import java.util.concurrent.*;

class LinkedTransferQueueAddExample1 {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 10; i <= 15; i++)
            queue.add(i);

        // Printing the elements of the queue
        System.out.println("The elements in the queue are:");
        for (Integer i : queue)
            System.out.print(i + " ");
    }
}
```

**Output:**

```java
The elements in the queue are:
10 11 12 13 14 15

```

**程序 2:** 在队列中添加字符串。

```java
// Java Program Demonstrate add()
// method of LinkedTransferQueue

import java.util.concurrent.*;

class LinkedTransferQueueAddExample2 {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<String>
            queue = new LinkedTransferQueue<String>();

        // Adding elements to this queue
        queue.add("a");
        queue.add("b");
        queue.add("c");
        queue.add("d");
        queue.add("e");

        // Printing the elements of the queue
        System.out.println("The elements in the queue are:");
        for (String i : queue)
            System.out.print(i + " ");
    }
}
```

**Output:**

```java
The elements in the queue are:
a b c d e

```

**程序 3:** 演示空指针异常

```java
// Java Program Demonstrate add()
// method of LinkedTransferQueue

import java.util.concurrent.*;

class LinkedTransferQueueAddExample2 {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<String>
            queue = new LinkedTransferQueue<String>();

        try {
            // Adding null to this queue
            queue.add(null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.NullPointerException

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # add(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#add(E))