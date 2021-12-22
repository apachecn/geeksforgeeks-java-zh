# Java 中 ArrayBlockingQueue size()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-size-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-size-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它将有一个固定的大小，你不能存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

**size()** 方法返回队列包含的元素的**数量。大小是一种重要的方法，通过计算队列容量和队列大小之间的差异，可以查看队列包含多少元素以及可以向该队列添加多少元素。
**语法:****

```
public int size()
```

**参数:**该方法不取任何参数。
**返回值:**该方法返回该队列中的元素数量。

下面的程序说明了 ArrayBlockingQueue 的 size()方法。
**节目一:**

```
// Program to Demonstrate the size() method
// of ArrayBlockingQueue.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

public static void main(String[] args) {
    // Define capacity of ArrayBlockingQueue
    int capacity = 5;

    // Create object of ArrayBlockingQueue
    ArrayBlockingQueue<Integer> queue = new 
                 ArrayBlockingQueue<Integer>(capacity);

    // Add elements to ArrayBlockingQueue
    queue.add(23);
    queue.add(32);
    queue.add(45);

    // Print size of queue after adding numbers
    int size=queue.size();
    System.out.println("After addding numbers"+
                              " Queue size = " +size);

    // Add more elements to ArrayBlockingQueue
    queue.add(88);
    queue.add(42);

    // Print size of queue after adding numbers
    size=queue.size();
    System.out.println("After addding more numbers"
                               +" Queue size = " +size);

} 
}
```

**Output:**

```
After addding numbers Queue size = 3
After addding more numbers Queue size = 5

```

**程序 2:**

```
// Program to demonstrate size() method of
// ArrayBlockingQueue.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

public static void main(String[] args) {
// Define capacity of ArrayBlockingQueue
    int capacity = 5;

    // Create object to store 5 names
    ArrayBlockingQueue<String> names = new 
             ArrayBlockingQueue<String>(capacity);

    // Add element to ArrayBlockingQueue
    names.add("Aman");
    names.add("Siddhant");

    // Print size of queue after adding numbers
    int size = names.size();
    System.out.println("After addding numbers"+
                            " Queue size = "+size);

    // Add more elements to ArrayBlockingQueue
    names.add("Raunak");
    names.add("Suvo");

    // Print size of queue after adding numbers
    size=names.size();
    System.out.println("After addding more numbers"+
                                 " Queue size = "+size);

} 
}
```

**Output:**

```
After addding numbers Queue size = 2
After addding more numbers Queue size = 4

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # size()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#size())