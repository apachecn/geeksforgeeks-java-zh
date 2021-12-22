# Java 中的 ArrayBlockingQueue peek()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-peek-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-peek-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它将有一个固定的大小，你不能存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

使用 **peek()** 方法返回队列的头。它检索但不删除该队列的头。如果队列为空，则此方法返回 null。
**语法:**

```java
public E peek()
```

**参数**:该方法不取任何参数。
**返回值:**该方法返回位于该队列头部的元素。
下面的程序说明了 ArrayBlockingQueue 的 peek()方法。
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to demonstrate peek() method of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

public static void main(String[] args) {
    // Define capacity of ArrayBlockingQueue
    int capacity = 5;

    // Create object of ArrayBlockingQueue
    ArrayBlockingQueue<Integer> queue =
         new ArrayBlockingQueue<Integer>(capacity);

    // Add element to ArrayBlockingQueue
    queue.add(23);
    queue.add(32);
    queue.add(45);
    queue.add(12);

    // Print queue after adding numbers
    System.out.println("After adding numbers queue is ");
    System.out.println(queue);

    // Print head of queue using peek() method
    System.out.println("Head of queue "+queue.peek());

}
}
```

**Output:** 

```java
After addding numbers queue is 
[23, 32, 45, 12]
Head of queue 23
```