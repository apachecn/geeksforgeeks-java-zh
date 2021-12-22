# Java 中 ArrayBlockingQueue put()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-put-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-put-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它将有一个固定的大小，你不能存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

如果队列未满， **put (E e)** 方法将作为参数传递的元素插入到该队列(ArrayBlockingQueue)尾部的方法中。如果**队列已满，那么它将等待空间变得可用。**
**语法:**

```
public void put(E e)  throws InterruptedException
```

**参数:**
e–要添加到队列中的元素。
**抛出**
中断异常——如果在等待时被中断。
NullPointerException–如果指定的元素为空。

下面的程序说明了数组锁定队列的放入方法。

**例 1**

```
// Java Program to demonstrate put(E e)
// method of ArrayBlockingQueue.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args) throws InterruptedException
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 5;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = new ArrayBlockingQueue<Integer>(capacity);

        // Add elements to ArrayBlockingQueue using put method
        queue.put(223);
        queue.put(546);
        queue.put(986);
        queue.put(357);
        queue.put(964);

        // print Queue
        System.out.println("queue contains " + queue);
    }
}
```

```
Output :
queue contains [223, 546, 986, 357, 964]

```

**例 2**

```
// Java Program to demonstrate put(E e)
// method of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args) throws InterruptedException
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 5;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<String> queue = new ArrayBlockingQueue<String>(capacity);

        // Add elements to ArrayBlockingQueue using put method
        queue.put("StarWars");
        queue.put("SuperMan");
        queue.put("Flash");
        queue.put("BatMan");
        queue.put("Avengers");

        // print Queue
        System.out.println("queue contains " + queue);

        // remove some elements
        queue.remove();
        queue.remove();

        // Add elements to ArrayBlockingQueue using put method
        queue.put("CaptainAmerica");
        queue.put("Thor");

        System.out.println("queue contains " + queue);
    }
}
```

```
Output :
queue contains [StarWars, SuperMan, Flash, BatMan, Avengers]
queue contains [Flash, BatMan, Avengers, CaptainAmerica, Thor]

```

**参考:**
[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # put(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#put(E))