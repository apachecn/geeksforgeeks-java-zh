# Java 中 ArrayBlockingQueue clear()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-clear-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-clear-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它会有一个固定的大小，你**可以不**存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

**clear()** 方法**从该队列中移除**所有元素。应用此方法后，队列将变空。
**语法:**

```java
public void clear()
```

下面的程序说明了 ArrayBlockingQueue 的 clear()方法。
**例 1**

```java
// Java Program Demonstrate clear()
// method of ArrayBlockingQueue.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 5;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue
            = new ArrayBlockingQueue<Integer>(capacity);

        // Add element to ArrayBlockingQueue
        queue.add(23);
        queue.add(32);
        queue.add(45);
        queue.add(12);

        // print queue after adding numbers
        System.out.println("After addding numbers");
        System.out.println(queue);

        // Apply clear() method
        queue.clear();

        // print queue after clear() operation
        System.out.println("After clear() method");
        System.out.println(queue);
    }
}
```

```java
Output :
After addding numbers
[23, 32, 45, 12]
After clear() method
[]

```

**例 2**

```java
// Java Program Demonstrate clear()
// method of ArrayBlockingQueue.
import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 5;

        // create object of ArrayBlockingQueue to store 5 names
        ArrayBlockingQueue<String> names
            = new ArrayBlockingQueue<String>(capacity);

        // Add element to ArrayBlockingQueue
        names.add("Aman");
        names.add("Siddhant");
        names.add("Mahafuj");
        names.add("Raunak");
        names.add("Suvo");

        // print queue after adding numbers
        System.out.println("List of Names: " + names);
        System.out.println("Remaining Capacity: " + names.remainingCapacity());

        // Apply clear() method
        names.clear();

        // print queue after clear() operation
        System.out.println("List of Names: " + names);
        System.out.println("Remaining Capacity: " + names.remainingCapacity());
    }
}
```

```java
Output :
List of Names: [Aman, Siddhant, Mahafuj, Raunak, Suvo]
Remaining Capacity: 0
List of Names: []
Remaining Capacity: 5

```

**参考:**
[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # clear()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#clear())