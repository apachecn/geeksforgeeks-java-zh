# 实现链接锁定请求应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-link edblockingreque-API/](https://www.geeksforgeeks.org/java-program-to-implement-linkedblockingdeque-api/)

在 JDK 1.6 中引入的 [**链接锁定设备**](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/) 类存在于[**Java . util . concurrent**](https://www.geeksforgeeks.org/java-util-concurrent-package/)包中。这是一个 deque，意思是一个双头队列。链接锁定请求的默认大小是整数。最大值。它实现了 BlockingDeque 类，并提供了基于链接节点的可选有界功能。这种可选的有界性是通过在构造函数中传递所需的大小来实现的，有助于防止内存浪费。如果一个线程试图从一个空的队列中移除元素，这个类将阻塞该线程。

实现**序列化**、**可迭代<E>T3】、**集合<E>T5】、[阻塞队列<E>T7】、](https://www.geeksforgeeks.org/blockingdeque-in-java/)[阻塞队列<E>T9】、](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/)[德清<E>T11】、](https://www.geeksforgeeks.org/deque-interface-java-example/)[队列<E>T13】接口，扩展](https://www.geeksforgeeks.org/queue-interface-java/)[抽象队列](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)****

**申报:**

```
public class LinkedBlockingDeque<E> extends AbstractQueue<E> implements 
BlockingDeque<E>, Serializable
```

这里， **E** 是集合中存储的元素类型。

**链接锁定请求 API 的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show the implementation
// of LinkedBlockingDeque API

import java.util.*;
import java.util.Collection;
import java.util.Iterator;
import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.TimeUnit;

class LinkedBlockingDequeImpl<E> {
    private LinkedBlockingDeque<E> linkedBlockingDeque;

    // constructor to create a LinkedBlockingDeque .
    public LinkedBlockingDequeImpl()
    {
        linkedBlockingDeque = new LinkedBlockingDeque<E>();
    }

    // constructor to create a LinkedBlockingDeque initially
    // containing the elements of the given collection
    public LinkedBlockingDequeImpl(
        Collection<? extends E> collection)
    {
        linkedBlockingDeque
            = new LinkedBlockingDeque<E>(collection);
    }

    // constructor to create a LinkedBlockingDeque with
    // specified capacity.
    public LinkedBlockingDequeImpl(int cap)
    {
        linkedBlockingDeque
            = new LinkedBlockingDeque<E>(cap);
    }

    // method to remove all of the elements from the deque.
    public void clear() { linkedBlockingDeque.clear(); }

    // method to check if deque contains the specified
    // element.
    public boolean contains(Object object)
    {
        return linkedBlockingDeque.contains(object);
    }

    // method to remove all of the elements from the deque
    // and add them to specified collection.
    public int drainTo(Collection<? super E> collection)
    {
        return linkedBlockingDeque.drainTo(collection);
    }

    // method to remove specified number of the elements
    // from the deque and add them to specified collection.
    public int drainTo(Collection<? super E> collection,
                       int maxElement)
    {
        return linkedBlockingDeque.drainTo(collection,
                                           maxElement);
    }

    // method to return an iterator over the elements in
    // this deque .
    public Iterator<E> iterator()
    {
        return linkedBlockingDeque.iterator();
    }

    // method to insert a specified element at the tail of
    // this queue. Return true upon successful insertion
    // else return false.
    public boolean offer(E element)
    {
        return linkedBlockingDeque.offer(element);
    }

    // method to insert a specified element at the tail of
    // this queue. Return true upon successful insertion
    // else return false.
    public boolean offer(E element, long timeout,
                         TimeUnit unit)
        throws InterruptedException
    {
        return linkedBlockingDeque.offer(element, timeout,
                                         unit);
    }

    // method to retrieve element from head of deque .
    public E peek() { return linkedBlockingDeque.peek(); }

    // method to remove and retrieve element from head of
    // deque .
    public E poll() { return linkedBlockingDeque.poll(); }

    // method to remove and retrieve element from head of
    // deque .
    public E poll(long timeout, TimeUnit unit)
        throws InterruptedException
    {
        return linkedBlockingDeque.poll(timeout, unit);
    }

    // method to insert the specified element at the tail of
    // the deque.
    public void put(E element) throws InterruptedException
    {
        linkedBlockingDeque.put(element);
    }

    // method to return the number of additional elements
    // that the deque can ideally accept without blocking.
    public int remainingCapacity()
    {
        return linkedBlockingDeque.remainingCapacity();
    }

    // method to remove a single instance of the
    // specified element from the deque
    public boolean remove(Object object)
    {
        return linkedBlockingDeque.remove(object);
    }

    // method to return the number of elements in the deque.
    public int size() { return linkedBlockingDeque.size(); }

    // method to retrieve and remove the head of the deque.
    public E take() throws InterruptedException
    {
        return linkedBlockingDeque.take();
    }

    // method to return an array containing all of
    // the elements in the deque.
    public Object[] toArray()
    {
        return linkedBlockingDeque.toArray();
    }

    // method to return an array containing all of
    // the elements in the deque
    public <T> T[] toArray(T[] array)
    {
        return linkedBlockingDeque.toArray(array);
    }

    // method to return a string representation of the
    // collection
    public String toString()
    {
        return linkedBlockingDeque.toString();
    }

    // method to insert specified element at the front of
    // the deque.
    public void addFirst(E element)
    {
        linkedBlockingDeque.addFirst(element);
    }

    // method to insert specified element at the end of the
    // deque.
    public void addLast(E element)
    {
        linkedBlockingDeque.addLast(element);
    }

    // method to retrieve first element of the deque.
    public void getFirst()
    {
        linkedBlockingDeque.getFirst();
    }

    // method to retrieve the last element of the deque.
    public void getLast() { linkedBlockingDeque.getLast(); }

    // Inserts the specified element at the front of this
    // deque
    public boolean offerFirst(E element)
    {
        return linkedBlockingDeque.offerFirst(element);
    }

    // method to insert a specified element at the end of
    // the deque.
    public boolean offerLast(E element)
    {
        return linkedBlockingDeque.offerLast(element);
    }

    // method to retrieve first element of the deque .
    public E peekFirst()
    {
        return linkedBlockingDeque.peekFirst();
    }

    // method to retrieve last element of the deque .
    public E peekLast()
    {
        return linkedBlockingDeque.peekLast();
    }
}

public class LinkedBlockingDequeDemo {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        // using LinkedBlockingDeque() constructor
        LinkedBlockingDequeImpl<Integer> linkedBlockingDeque
            = new LinkedBlockingDequeImpl<Integer>();

        try {

            // Add numbers to end of LinkedBlockingDeque
            linkedBlockingDeque.put(10);
            linkedBlockingDeque.put(20);
            linkedBlockingDeque.put(30);
        }

        catch (InterruptedException e)
        {
            e.printStackTrace();
        }

        System.out.println(
            "the elements of the linkedBlockingDeque is ");

        Iterator<Integer> itr = linkedBlockingDeque.iterator();

        while (itr.hasNext())
        {
            System.out.print(itr.next() + "\t");
        }

        System.out.println();

        linkedBlockingDeque.offer(60);
        linkedBlockingDeque.offer(70);

        System.out.println(
            "the peak element of the linkedBlockingDeque is(by peeking) "
            + linkedBlockingDeque.peek());

        System.out.println(
            "the peak element of the linkedBlockingDeque is(by polling) "
            + linkedBlockingDeque.poll());

        System.out.println(
            "the remaining capacity is "
            + linkedBlockingDeque.remainingCapacity());

        System.out.println(
            "element 30 removed "
            + linkedBlockingDeque.remove(30));

        System.out.println(
            "the linkedBlockingDeque contains 40 :"
            + linkedBlockingDeque.contains(40));

        System.out.println(
            "the linkedBlockingDeque contains 10 :"
            + linkedBlockingDeque.contains(10));

        System.out.println(
            "the size of the linkedBlockingDeque is "
            + linkedBlockingDeque.size());

        System.out.println(linkedBlockingDeque);
    }
}
```

**Output**

```
the elements of the linkedBlockingDeque is 
10    20    30    
the peak element of the linkedBlockingDeque is(by peeking) 10
the peak element of the linkedBlockingDeque is(by polling) 10
the remaining capacity is 2147483643
element 30 removed true
the linkedBlockingDeque contains 40 :false
the linkedBlockingDeque contains 10 :false
the size of the linkedBlockingDeque is 3
[20, 60, 70]
```