# Java 中 ArrayBlockingQueue add()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-add-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-add-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它会有一个固定的大小，你**可以不**存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

**add (E e)** 方法将作为参数传递的元素插入该队列的**尾部**处的方法。如果添加元素超出了队列的容量，那么该方法将抛出一个 IllegalStateException。如果元素添加成功，此方法返回 true，否则将引发 IllegalStateException。
**语法:**

```
public boolean add(E e)
```

**参数:**
e–要添加到队列中的元素。
**返回值:**
如果添加成功则为真。
**抛出:**
illegalstatexception–如果此队列已满
null pointerexception–如果指定的元素为空

**示例 1**
下面的程序说明了向 ArrayBlockingQueue 添加元素。

```
// Java Program to Demonstrate add(E e) method
// of ArrayBlockingQueue.
import java.util.ArrayList;
import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 10;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = new ArrayBlockingQueue<Integer>(capacity);

        // Add element to ArrayBlockingQueue
        queue.add(23);

        // print queue after add operation
        System.out.println("After adding 23");
        System.out.println(queue);

        // add more numbers
        queue.add(32);
        queue.add(45);
        queue.add(12);

        // print queue after add operation
        System.out.println("After adding 32, 45, 12");
        System.out.println(queue);

        // add more numbers
        queue.add(27);
        queue.add(67);

        // print queue after add operation
        System.out.println("After adding 27, 67");
        System.out.println(queue);
    }
}
```

```
Output :
After adding 23
[23]
After adding 32, 45, 12
[23, 32, 45, 12]
After adding 27, 67
[23, 32, 45, 12, 27, 67]

```

**示例 2**
下面的程序演示了向 ArrayBlockingQueue 添加元素，以及如果队列已满时引发的异常。

```
// Java Program to Demonstrate add(E e) method
// of ArrayBlockingQueue.
import java.util.ArrayList;
import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {

        // define capacity of ArrayBlockingQueue to 5 elements
        int capacity = 5;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = new ArrayBlockingQueue<Integer>(capacity);

        // Add 5 element to ArrayBlockingQueue
        queue.add(23);
        queue.add(32);
        queue.add(45);
        queue.add(12);
        queue.add(27);

        // print queue after add operation
        System.out.println("After adding all 5 elements to queue");
        System.out.println(queue);

        // check whether queue is full or not.
        if (queue.remainingCapacity() == 0) {
            System.out.println("Queue is full");
        }
        else {
            System.out.println("Queue is not full");
        }

        // try to add more elements
        // If exception thrown print the exception.
        try {
            Boolean response = queue.add(27);
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

```
Output :
After adding all 5 elements to queue
[23, 32, 45, 12, 27]
Queue is full
java.lang.IllegalStateException: Queue full
    at java.util.AbstractQueue.add(Unknown Source)
    at java.util.concurrent.ArrayBlockingQueue.add(Unknown Source)
    at defaultpackage.GFG.main(GFG.java:38)

```

**参考:**
[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # add(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#add(E))