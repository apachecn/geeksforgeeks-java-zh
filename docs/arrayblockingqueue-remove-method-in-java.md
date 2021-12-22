# Java 中的 ArrayBlockingQueue remove()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-remove-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-remove-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它会有一个固定的大小，你**可以不**存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

**移除(对象 o)** 方法**从该队列中移除指定元素的单个实例**，如果它存在的话。
我们可以说，如果这个队列包含一个或多个这样的元素，那么这个方法移除一个元素 e，使得 o 等于(e)。如果此队列包含我们要移除的指定元素，Remove()方法将返回 true。

**语法:**

```java
public boolean remove(Object o)
```

**参数:**
o–要从该队列中删除的元素(如果存在)。
**返回:**
如果该队列包含我们想要移除的指定元素，则返回真。

下面的程序说明了数组锁定队列的移除方法。

**例 1**

```java
// Java Program Demonstrate remove(Object o)
// method of ArrayBlockingQueue.
import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args) throws InterruptedException
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 5;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue
            = new ArrayBlockingQueue<Integer>(capacity);

        // Add elements to ArrayBlockingQueue using put method
        queue.put(223);
        queue.put(546);
        queue.put(986);

        // print Queue
        System.out.println("queue contains " + queue);

        // remove 223
        boolean response = queue.remove(223);
        // print Queue
        System.out.println("Removal of 223 :" + response);

        // print Queue
        System.out.println("queue contains " + queue);

        // remove 546
        response = queue.remove(546);
        // print Queue
        System.out.println("Removal of 546 :" + response);

        // print Queue
        System.out.println("queue contains " + queue);

        // remove 734 which is not present
        response = queue.remove(734);
        // print Queue
        System.out.println("Removal of 734 :" + response);

        // print Queue
        System.out.println("queue contains " + queue);
    }
}
```

```java
Output :
queue contains [223, 546, 986]
Removal of 223 :true
queue contains [546, 986]
Removal of 546 :true
queue contains [986]
Removal of 734 :false
queue contains [986]

```

**例 2**

```java
// Java Program Demonstrate remove(Object o)
// method of ArrayBlockingQueue.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args) throws InterruptedException
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 5;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<String> queue
            = new ArrayBlockingQueue<String>(capacity);

        // Add elements to ArrayBlockingQueue using put method
        queue.put("StarWars");
        queue.put("SuperMan");
        queue.put("Flash");
        queue.put("BatMan");
        queue.put("Avengers");

        // print Queue
        System.out.println("queue contains " + queue);

        // remove StarWars
        boolean response = queue.remove("StarWars");
        // print Queue
        System.out.println("Removal of StarWars :" + response);

        // print Queue
        System.out.println("queue contains " + queue);

        // remove Hulk
        response = queue.remove("Hulk");
        // print Queue
        System.out.println("Removal of Hulk :" + response);

        // print Queue
        System.out.println("queue contains " + queue);
    }
}
```

```java
Output :
queue contains [StarWars, SuperMan, Flash, BatMan, Avengers]
Removal of StarWars :true
queue contains [SuperMan, Flash, BatMan, Avengers]
Removal of Hulk :false
queue contains [SuperMan, Flash, BatMan, Avengers]

```

**参考:**
[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # remove(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#remove(java.lang.Object))