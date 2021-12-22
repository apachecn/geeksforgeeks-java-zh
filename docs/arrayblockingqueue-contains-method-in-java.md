# ArrayBlockingQueue 在 Java 中包含()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-contains-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-contains-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它会有一个固定的大小，你**可以不**存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

如果队列包含作为参数传递的对象，则**包含(对象 o)** 方法返回真**。我们可以说方法返回真**当且仅当**这个队列包含至少一个元素 e，它等于作为参数传递的对象 o，即 o.equals(e)。
**语法:****

```java
public boolean contains(Object o)
```

**参数:**
o–检查队列是否包含指定对象的对象。
**返回值:**
如果该队列包含对象，则为真

下面的程序示例包含了 ArrayBlockingQueue 的方法。
**例 1**

```java
// Java Program Demonstrate contains(Object o)
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

        // Add elements to ArrayBlockingQueue
        queue.add(23);
        queue.add(32);
        queue.add(45);
        queue.add(12);

        // check whether queue contains 23
        boolean response1 = queue.contains(23);

        // print after applying contains method with 23 as parameter
        System.out.println("queue contains 23 : " + response1);

        // check whether queue contains 99
        boolean response2 = queue.contains(99);

        // print after applying contains method with 99 as parameter
        System.out.println("queue contains 99 : " + response2);
    }
}
```

**Output:**

```java
queue contains 23 : true
queue contains 99 : false

```

**例 2**

```java
// Java Program Demonstrate contains(Object o)
// method of ArrayBlockingQueue.
import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    // create a User Object with name and age as attribute
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
        gfg.containsMethodExample();
    }

    // Method to give example of contains function
    public void containsMethodExample()
    {

        // define capacity of ArrayBlockingQueue
        int capacity = 5;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<User> queue
            = new ArrayBlockingQueue<User>(capacity);

        User user1 = new User("Aman", "24");
        User user2 = new User("Amar", "23");
        User user3 = new User("Sanjeet", "25");
        User user4 = new User("Suvo", "26");

        // Add Objects to ArrayBlockingQueue
        queue.add(user1);
        queue.add(user2);
        queue.add(user3);
        queue.add(user4);

        User user5 = new User("Ravi", "22");
        // check whether queue contains User1
        boolean response1 = queue.contains(user1);

        // print after applying contains method with user1 as parameter
        System.out.println("queue contains User having name "
                           + user1.name + " : " + response1);

        // check whether queue contains User5
        boolean response2 = queue.contains(user5);

        // print after applying contains method with user1 as parameter
        System.out.println("queue contains User having name "
                           + user5.name + " : " + response2);
    }
}
```

**Output:**

```java
queue contains User having name Aman : true
queue contains User having name Ravi : false

```

**参考:**
[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # contains(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#contains(java.lang.Object))