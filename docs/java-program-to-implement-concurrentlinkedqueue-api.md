# 实现并发链接队列应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-concurrentlinkedqueue-api/](https://www.geeksforgeeks.org/java-program-to-implement-concurrentlinkedqueue-api/)

Java 中的[**ConcurrentLinkedQueue**](https://www.geeksforgeeks.org/concurrentlinkedqueue-in-java-with-examples/)类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分。属于[**Java . util . concurrent**](https://www.geeksforgeeks.org/java-util-concurrent-package/)包。它是在 JDK 1.5 中引入的。用于同时借助 [链表](https://www.geeksforgeeks.org/linked-list-in-java/)实现[队列](https://www.geeksforgeeks.org/queue-data-structure/)。这是队列的一种无边界线程安全实现，它以先进先出的方式在队列尾部插入元素。当多个线程共享一个无界队列时，可以使用它。

为了实现并发链接队列应用编程接口，我们首先创建一个类“并发链接队列实现”，并在这个类中创建队列的所有方法。

**并发链接队列应用编程接口的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the
// implementation of ConcurrentLinkedQueue API

import java.util.Collection;
import java.util.Iterator;
import java.util.concurrent.ConcurrentLinkedQueue;

class ConcurrentLinkedQueueImplmentation<E> {

    private ConcurrentLinkedQueue<E> concurrentLinkedQueue;

    // Constructor creates a new empty ConcurrentLinkedQueue
    public ConcurrentLinkedQueueImplmentation()
    {

        // New empty concurrentLinkedQueue
        concurrentLinkedQueue = new ConcurrentLinkedQueue<>();
    }

    // Constructor creates a new ConcurrentLinkedQueue of
    // type E
    public ConcurrentLinkedQueueImplmentation(Collection<? extends E> c)
    {
        // New empty concurrentLinkedQueue
        concurrentLinkedQueue = new ConcurrentLinkedQueue<>(c);
    }

    // Add specified element to the tail of the queue
    public boolean add(E e)
    {
        // Add element
        return concurrentLinkedQueue.add(e);
    }

    // Returns true if the queue contains the specified
    // element
    public boolean contains(Object o)
    {
        return concurrentLinkedQueue.contains(o);
    }

    // Returns an iterator over the elements of the queue
    public Iterator<E> iterator()
    {
        return concurrentLinkedQueue.iterator();
    }

    // Add the specified element at the tail of the queue
    public boolean offer(E e)
    {
        return concurrentLinkedQueue.offer(e);
    }

    // Returns the peek of the queue or returns null if this
    // queue is empty.
    public E peek() { return concurrentLinkedQueue.peek(); }

    // Retrieves and removes the head of this queue, or
    // returns null if this queue is empty

    public E poll() { return concurrentLinkedQueue.poll(); }

    // Removes a single instance of the specified element
    // from this queue, if it is present.
    public boolean remove(Object o)
    {
        return concurrentLinkedQueue.remove(o);
    }

    // Returns the size of the queue
    public int size()
    {
        return concurrentLinkedQueue.size();
    }

    // Returns an array containing all of the elements in
    // this queue
    public Object[] toArray()
    {
        return concurrentLinkedQueue.toArray();
    }

    // Returns an array containing all of the elements in
    // this queue, in proper sequence; the return type of
    // the array is that of the specified
    //  array.
    public <T> T[] toArray(T[] a)
    {
        return concurrentLinkedQueue.toArray(a);
    }
}

public class GFG {
    public static void main(String[] arg)
    {

        // New ConcurrentLinkedQueue
        ConcurrentLinkedQueueImplmentation<Integer>
            concurrentLinkedQueue
            = new ConcurrentLinkedQueueImplmentation<
                Integer>();

        // Adding elements to the ConcurrentLinkedQueue
        concurrentLinkedQueue.add(10);
        concurrentLinkedQueue.add(20);
        concurrentLinkedQueue.add(30);
        concurrentLinkedQueue.add(40);
        concurrentLinkedQueue.add(50);

        System.out.println(
            "The elements of the ConcurrentLinkedQueue is:");

        // Iterator to iterate over ConcurrentLinkedQueue
        Iterator<Integer> it
            = concurrentLinkedQueue.iterator();

        // Iterate over ConcurrentLinkedQueue
        while (it.hasNext())
        {
            System.out.print(it.next() + " ");
        }

        System.out.println();

        // Print the size of the queue
        System.out.println("Size of the concurrentLinkedQueue is: "
            + concurrentLinkedQueue.size());

        System.out.println();

        // Print Peek element of the queue
        System.out.println("The peek element of the concurrentLinkedQueue is: "
            + concurrentLinkedQueue.peek());

        System.out.println();

        // Print the polled element of the queue
        System.out.println("The polled element of the concurrentLinkedQueue is: "
            + concurrentLinkedQueue.poll());

        System.out.println();

        // Remove specified element to the queue, returns
        // true if removed successfully or returns null if
        // element not present in the queue
        System.out.println("Remove 30: "
            + concurrentLinkedQueue.remove(30));

        System.out.println();

        // Check whether the spaecified element is present
        // or not in the queue
        System.out.println("The concurrentLinkedQueue contains 40:"
            + concurrentLinkedQueue.contains(40));

        System.out.println();

        // Print the size of the queue
        System.out.println("Size of the concurrentLinkedQueue is: "
            + concurrentLinkedQueue.size());
    }
}
```

**Output**

```
The elements of the ConcurrentLinkedQueue is:
10 20 30 40 50 
Size of the concurrentLinkedQueue is: 5

The peek element of the concurrentLinkedQueue is: 10

The polled element of the concurrentLinkedQueue is: 10

Remove 30: true

The concurrentLinkedQueue contains 40:true

Size of the concurrentLinkedQueue is: 3
```