# 实现链接锁定队列 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-linkedblockingqueue-api/](https://www.geeksforgeeks.org/java-program-to-implement-linkedblockingqueue-api/)

[LinkedBlockingQueue](https://www.geeksforgeeks.org/linkedblockingqueue-class-in-java/) API 是基于链接节点的可选有界队列。它以先进先出的顺序排列元素。这个队列的头是在队列中存在时间最长的元素，队列的尾是在队列中存在时间最短的元素。新元素被插入到队列的尾部，队列检索操作获取队列头部的元素。属于 java.util.concurrent package。它扩展了对象、抽象集合和抽象队列类。

容量参数是防止队列过度扩展的一种方法。容量(如果未指定)等于整数。最大值。每次插入时都会动态创建链接节点，除非这会使队列超出容量。

LinkedBlockingQueue API 是 Java 集合框架的成员。

**所有实现的接口:**

```java
1\. Serializable
2\. Iterable<E>
3\. Collection<E>
4\. BlockingQueue<E>
5\. Queue<E>
```

**参数:** E —集合中元素的类型

**语法:**

```java
public class LinkedBlockingQueue<E> extends AbstractQueue<E>
implements BlockingQueue<E>, Serializable
```

**施工人员:**

1.  public LinkedBlockingQueue()–创建一个容量为整数的 LinkedBlockingQueue。最大值。
2.  公共链接锁定队列(集合 extends E>c)–创建一个容量为整数的链接锁定队列。MAX_VALUE，最初包含指定集合的元素。
3.  公共链接锁定队列(整数容量)-创建具有给定容量的链接锁定队列。

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement LinkedBlockingQueue API

import java.util.Collection;
import java.util.Iterator;
import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.TimeUnit;

public class BlockingQueue<E> {
    private LinkedBlockingQueue<E> q;

    // Creates a LinkedBlockingQueue with a size of
    // Integer.MAX_VALUE.
    public BlockingQueue()
    {
        q = new LinkedBlockingQueue<E>();
    }

    // Creates a LinkedBlockingQueue initially containing
    // the elements of the given collection
    public BlockingQueue(Collection<? extends E> c)
    {
        q = new LinkedBlockingQueue<E>(c);
    }

    // Creates a LinkedBlockingQueue with the given size
    public BlockingQueue(int size)
    {
        q = new LinkedBlockingQueue<E>(size);
    }

    // Returns true if the queue contains the given element
    public boolean contains(Object o)
    {
        return q.contains(o);
    }

    // Removes all elements from the queue and adds them to
    // the given collection.
    public int drainTo(Collection<? super E> c)
    {
        return q.drainTo(c);
    }

    //  Removes the elements from the queue and adds them to
    //  the given collection.
    public int drainTo(Collection<? super E> c, int maxEle)
    {
        return q.drainTo(c, maxEle);
    }

    // Returns an iterator over the elements in the queue
    public Iterator<E> iterator() { return q.iterator(); }

    // removes all the elements from the queue.
    void clear() { q.clear(); }

    // Inserts the given element at the end of the queue,
    // returning true upon inserting and false if the queue
    // is full.
    public boolean offer(E e) { return q.offer(e); }

    // inserts then given element at the end and wait for
    // the given time for the space to become available
    public boolean offer(E e, long timeout, TimeUnit unit)
        throws InterruptedException
    {
        return q.offer(e, timeout, unit);
    }

    // Retrieves, but does not remove, the head of the
    // queue, or returns null if this queue is empty.
    public E peek() { return q.peek(); }

    //  Retrieves and removes the head of the queue
    public E poll() { return q.poll(); }

    // Retrieves and removes the head of the queue and wait
    // for the specified time for the element to become
    // available.
    public E poll(long tout, TimeUnit un)
        throws InterruptedException
    {
        return q.poll(tout, un);
    }

    // Returns the number of additional elements that the
    // queue can contain without blocking.
    public int remainingCapacity()
    {
        return q.remainingCapacity();
    }

    // Removes the specified element from the queue
    public boolean remove(Object o) { return q.remove(o); }

    // Returns the number of elements in the queue
    public int size() { return q.size(); }

    // Inserts the given element at the end of the queue,
    // wait for space to become available
    public void put(E e) throws InterruptedException
    {
        q.put(e);
    }

    // Retrieves and removes the head of the queue wait till
    // an element becomes available
    public E take() throws InterruptedException
    {
        return q.take();
    }

    // Returns an array containing all the elements in the
    // queue.
    public Object[] toArray() { return q.toArray(); }

    // Returns an array containing all of the elements in
    // the queue
    public <T> T[] toArray(T[] a) { return q.toArray(a); }

    // Returns a string representation of th collection.
    public String toString() { return q.toString(); }

    public static void main(String[] args)
    {
        BlockingQueue<Integer> q
            = new BlockingQueue<Integer>();
        try {
            q.put(1);
            q.put(2);
            q.put(3);
        }
        catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println(
            "The elements of the LinkedBlockingQueue is ");

        Iterator<Integer> i = q.iterator();

        while (i.hasNext()) {
            System.out.print(i.next() + "\t");
        }
        System.out.println();

        System.out.println("The remaining capacity is "
                           + q.remainingCapacity());

        System.out.println("3 removed " + q.remove(3));

        q.offer(6);
        q.offer(7);

        System.out.println(
            "The peak element of the LinkedBlockingQueue is "
            + q.peek());

        System.out.println(
            "The peak element of the LinkedBlockingQueue is "
            + q.poll());

        System.out.println(
            "The LinkedBlockingQueue contains 4 :"
            + q.contains(4));

        System.out.println(
            "The LinkedBlockingQueue contains 1 :"
            + q.contains(1));

        System.out.println(
            "The size of the LinkedBlockingQueue is "
            + q.size());

        System.out.println(q);
    }
}
```

**Output**

```java
The elements of the LinkedBlockingQueue is 
1    2    3    
The remaining capacity is 2147483644
3 removed true
The peak element of the LinkedBlockingQueue is 1
The peak element of the LinkedBlockingQueue is 1
The LinkedBlockingQueue contains 4 :false
The LinkedBlockingQueue contains 1 :false
The size of the LinkedBlockingQueue is 3
[2, 6, 7]

```

**Output**

```java
The elements of the LinkedBlockingQueue is 
1    2    3    
The remaining capcity is 2147483644
3 removed true
The peak element of the LinkedBlockingQueue is 1
The peak element of the LinkedBlockingQueue is 1
The LinkedBlockingQueue contains 4 :false
The LinkedBlockingQueue contains 1 :false
The size of the LinkedBlockingQueue is 3
[2, 6, 7]
```

**方法:**

<figure class="table">

| **方法** | **类型** | **描述** |
| --- | --- | --- |
| 清除() | 空的 | 移除 LinkedBlockingQueue 的所有元素 |
| 包含(对象 0) | 布尔 | 如果队列包含指定的元素，则返回 true。 |
| 迭代器() | 迭代器(<e>)</e> | 返回队列中元素的迭代器。 |
| 要约 | 布尔 | 如果可能，将指定的元素插入该队列的尾部，并在成功时返回 true，否则返回 false。 |
| 报价(长时间超时，时间单位单位) | 布尔 | 在队列的尾部插入指定的元素，并等待指定的时间使空间变得可用。 |
| peek() | E | 检索但不移除队列头。 |
| 民意测验() | E | 检索并移除队列头。 |
| 放(英) | 空的 | 在这个队列的尾部插入指定的元素，必要时等待空间变得可用。 |
| 剩余容量() | （同 Internationalorganizations）国际组织 | 返回此队列在没有阻塞的情况下理想情况下可以接受的附加元素的数量。 |
| 大小() | （同 Internationalorganizations）国际组织 | 返回队列的大小 |
| toarray() | 对象[] | 将队列转换为数组 |
| 排水(集合〔t0〕c) | （同 Internationalorganizations）国际组织 | 从队列中移除所有可用元素，并将它们添加到指定的集合中。 |
| take() | E | 检索并移除该队列的头，如有必要，等待直到某个元素变得可用。 |
| 移除(对象 0) | 布尔 | 从队列中移除指定的元素(如果存在)。 |

</figure>