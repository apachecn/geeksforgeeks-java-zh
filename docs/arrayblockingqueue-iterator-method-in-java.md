# Java 中的 ArrayBlockingQueue 迭代器()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-iterator-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-iterator-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类的**迭代器()**方法用于以适当的顺序返回与该队列相同元素的迭代器。从这个方法返回的元素包含从第一个(头)到最后一个(尾)的元素。返回的迭代器弱一致。

**语法:**

```java
public Iterator iterator()
```

**返回值:**该方法以正确的顺序返回与 ArrayBlockingQueue 中存在的元素相同的迭代器。

下面的程序说明了 ArrayBlockingQueue 类的迭代器()方法:

**程序 1:**

```java
// Program Demonstrate how to apply iterator() method
// of ArrayBlockingQueue Class.

import java.util.concurrent.ArrayBlockingQueue;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = new 
                ArrayBlockingQueue<Integer>(capacity);

        // Add 5 elements to ArrayBlockingQueue
        queue.offer(423);
        queue.offer(422);
        queue.offer(421);
        queue.offer(420);
        queue.offer(424);

        // Print queue
        System.out.println("Queue is " + queue);

        // Call iterator() method and Create an iterator
        Iterator iteratorValues = queue.iterator();

        // Print elements of iterator
        System.out.println("\nThe iterator values:");
        while (iteratorValues.hasNext()) {
            System.out.println(iteratorValues.next());
        }
    }
}
```

**输出:**

```java
Queue is [423, 422, 421, 420, 424]

The iterator values:
423
422
421
420
424

```

**程序二:**

```java
// Program Demonstrate how to apply iterator() method
// of ArrayBlockingQueue Class.

import java.util.concurrent.ArrayBlockingQueue;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<String> queue = new 
                  ArrayBlockingQueue<String>(capacity);

        // Add 5 elements to ArrayBlockingQueue
        queue.offer("User");
        queue.offer("Employee");
        queue.offer("Manager");
        queue.offer("Analyst");
        queue.offer("HR");

        // Print queue
        System.out.println("Queue is " + queue);

        // Call iterator() method and Create an iterator
        Iterator iteratorValues = queue.iterator();

        // Print elements of iterator
        System.out.println("\nThe iterator values:");
        while (iteratorValues.hasNext()) {
            System.out.println(iteratorValues.next());
        }
    }
}
```

**输出:**

```java
Queue is [User, Employee, Manager, Analyst, HR]

The iterator values:
User
Employee
Manager
Analyst
HR

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/arrayblockingqueue . html #迭代器](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#iterator--)