# Java 中 ArrayBlockingQueue remaingccapacity()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-remainingcapacity-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-remainingcapacity-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它会有一个固定的大小，你**不能存储**数量超过队列容量的元素。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

**remainingCapacity()** 方法返回可以添加到队列中而不会阻塞的更多元素的数量。这始终等于该队列的初始容量与该队列的当前大小之差。

**语法:**

```java
public int remainingCapacity()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回队列的剩余容量。

下面的程序说明了 ArrayBlockingQueue 的 remainingCapacity()方法:
**程序 1:**

```java
// Program to demonstrate remainingCapacity() method
// of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = new 
            ArrayBlockingQueue<Integer>(capacity);

        // Add elements to ArrayBlockingQueue
        queue.add(23);
        queue.add(32);

        // Print queue after adding numbers
        System.out.println("Queue :" + queue);
        // Check remaining capacity
        int remainingCapacity = queue.remainingCapacity();
        System.out.println("Remaining Capacity:" + 
                                       remainingCapacity);

        // Add elements to ArrayBlockingQueue
        queue.add(54);
        queue.add(78);

        // Print queue after adding numbers
        System.out.println("Queue :" + queue);
        // Check remaining capacity
        System.out.println("Remaining Capacity:" + 
                               queue.remainingCapacity());
    }
}
```

**Output:**

```java
Queue :[23, 32]
Remaining Capacity:3
Queue :[23, 32, 54, 78]
Remaining Capacity:1

```

**程序 2:**

```java
// Program to demonstrate remainingCapacity() method
// of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {
    // Create a User Object with name and age as an attribute
    public class User {

        public String name;
        public String age;
        User(String name, String age)
        {
            this.name = name;
            this.age = age;
        }
    }

    // Main Method
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.RemainingCapacityExample();
    }
    // Method to give example of contains function
    public void RemainingCapacityExample()
    {

        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<User> queue = new 
                  ArrayBlockingQueue<User>(capacity);

        // Create user objects
        User user1 = new User("Aman", "24");
        User user2 = new User("Amar", "23");
        User user3 = new User("Sanjeet", "25");

        // Add Objects to ArrayBlockingQueue
        queue.offer(user1);
        queue.offer(user2);
        queue.offer(user3);

        // Check remaining capacity
        int remainingCapacity = queue.remainingCapacity();
        System.out.println("Remaining Capacity:" + 
                                       remainingCapacity);

        User user4 = new User("Suvo", "26");
        User user5 = new User("Ravi", "22");

        // Adding more objects
        queue.offer(user2);
        queue.offer(user3);

        // Check remaining capacity
        remainingCapacity = queue.remainingCapacity();
        System.out.println("Remaining Capacity:" + 
                                     remainingCapacity);
    }
}
```

**Output:**

```java
Remaining Capacity:2
Remaining Capacity:0

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # remainingCapacity()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#remainingCapacity())