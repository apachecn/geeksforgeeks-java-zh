# Java 中 LinkedTransferQueue take()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-take-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-take-method-in-java/)

**java . util . concurrent . linkedtransferqueue . take()**方法是 Java 中的内置函数，它检索并移除队列的第一个元素。此方法还会等待(如果需要)直到某个元素变得可用。
**语法:**

```java
LinkedTransferQueue.take()  

```

**参数:**函数不接受任何参数。

**返回值:**函数返回队列的第一个元素。

**异常:**如果在等待过程中被中断，该功能将抛出*中断异常*。

下面的程序说明了 Java . util . concurrent . linkedtransferqueue . take():

**程序 1:**

```java
// Java Program Demonstrate take()
// method of LinkedTransferQueue 

import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueTakeExample1 {
    public static void main(String[] args) throws Exception
    {
        // Initializing the queue
        LinkedTransferQueue<String> queue = 
                        new LinkedTransferQueue<String>();

        // Adding elements to this queue
        queue.add("Alex");
        queue.add("Bob");
        queue.add("Chuck");
        queue.add("Drake");
        queue.add("Eric");

        // Printing the elements
        System.out.println("Elements are :");
        for (String xyz : queue) {
            // will take and remove the head of the queue
            System.out.println(queue.take());
        }

        // Printing the size of the Queue
        System.out.println("Queue Size: " + queue.size());
    }
}
```

**Output:**

```java
Elements are :
Alex
Bob
Chuck
Drake
Eric
Queue Size: 0

```

**程序 2:**

```java
// Java Program Demonstrate take()
// method of LinkedTransferQueue 

import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueTakeExample2 {
    public static void main(String[] args) throws Exception
    {
        // Initializing the queue
        LinkedTransferQueue<Integer> queue = 
                        new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 1; i <= 5; i++)
            queue.add(i);

        // Printing the elements
        System.out.println("Elements are :");
        for (Integer xyz : queue) {
            // will take and remove the head of the queue
            System.out.println(queue.take());
        }
        // Printing the size of the Queue
        System.out.println("Queue Size: " + queue.size());
    }
}
```

**Output:**

```java
Elements are :
1
2
3
4
5
Queue Size: 0

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # take()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#take())