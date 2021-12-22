# 实现延迟队列 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-delayqueue-api/](https://www.geeksforgeeks.org/java-program-to-implement-delayqueue-api/)

[DelayQueue 类](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/)属于 java.util.concurrent 包。延迟队列实现了[阻塞队列接口](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/)。延迟队列是一个专门的优先级队列，它对支持其延迟时间的元素进行排序。这意味着只有那些元素可以从已经过期的队列中取出。DelayQueue 头包含在最短时间内过期的元素。

一种由延迟元素组成的无界阻塞队列，其中一个元素只能在其延迟过期时被取用。队列的头部是延迟在过去过期时间最长的延迟元素。如果没有延迟过期，则没有头，**轮询将返回空值。当一个元素的 getDelay(TimeUnit。方法返回一个小于或等于零的值。即使无法使用 take 或 poll 移除未过期的元素，它们也会被视为正常元素。例如，size 方法返回过期和未过期元素的计数。此队列不允许空元素。**

****程序:****

*   **创建一个初始为空的新延迟队列。DelayQueue 类提供了两个构造函数，一个没有参数，另一个从另一个集合中获取元素:**

> **延迟队列()**
> 
>  **延迟队列(集合 extends E> c)**

*   **创建一个延迟队列，最初包含给定延迟实例集合的元素。**
*   **现在，使用类“布尔加法(E e)”将所有指定的元素插入这个延迟队列。**
*   **从延迟队列中检索并移除元素。**

****实施:****

*   ****步骤 1** :创建一个初始为空的新延迟队列。**
*   ****步骤 2** :创建一个延迟队列，最初包含延迟实例集合的元素。**
*   ****第三步**:将指定的元素插入这个延迟队列。**
*   ****第 4 步**:从此队列中移除所有可用的元素，并将它们添加到给定的集合中。**
*   ****步骤 5** :从队列中最多移除给定数量的可用元素，并将它们添加到给定的集合中。**
*   ****第 6 步**:如果可能的话，在这个队列的尾部插入指定的元素，这样做不会超出队列的容量。**
*   ****第 7 步**:将指定元素插入延迟队列。**
*   ****第 8 步**:检索但不删除该队列的头，如果该队列为空，则简单返回空。

    *   步骤 8(a):检索并删除该队列的头，如果该队列为空，则返回空值。
    *   步骤 8(b):检索并删除队列头，如有必要，等待直到具有过期延迟的元素在该队列中可用。** 
*   ****第九步**:将指定元素插入延迟队列。**
*   ****步骤 10** :从该队列中移除指定元素的单个实例(如果存在的话)。**
*   ****第 11 步**:检索并删除该队列的头，如有必要，等待直到该队列中有一个具有过期延迟的元素可用。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to implement DelayQueue API

// Importing classes from
// java.util package
import java.util.Collection;
import java.util.Iterator;
import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

// Class
public class DelayQueueImpl<E extends Delayed> {
    private DelayQueue<E> delayQueue;

    // Method 1
    public DelayQueueImpl()
    {
        // Step 1: Create a new DelayQueue
        // that is initially empty
        delayQueue = new DelayQueue<E>();
    }

    // Method 2 - Creating delayQueue
    // for containing elements
    public DelayQueueImpl(Collection<? extends E> c)
    {

        // Step 2: Creates a DelayQueue initially containing
        // elements of collection of Delayed instances
        delayQueue = new DelayQueue<>(c);
    }

    // Method 3
    // Step 3: Inserts the specified element
    // into this delay queue
    public boolean add(E e) { return delayQueue.add(e); }

    // Method 4
    public void clear()
    {
        // Automatically removes all of the elements
        // from this queue
        delayQueue.clear();
    }

    // Method 5
    public boolean contains(Object o)
    {
        // Returns true if this queue contains the specified
        // element else return false
        return delayQueue.contains(o);
    }

    // Method 6
    public int drainTo(Collection<? super E> c)
    {
        // Step 4: Removes all available elements from this
        // queue and adds them to the given collection.
        return delayQueue.drainTo(c);
    }

    // Method 7
    // Step 5: Removes at most the given number of available
    // elements from queue and adds them to the given
    // collection
    public int drainTo(Collection<? super E> c,
                       int maxElements)
    {
        return delayQueue.drainTo(c, maxElements);
    }

    // Method 8
    public Iterator<E> iterator()
    {
        // Returns an iterator over the elements
        // in this queue in proper sequence
        return delayQueue.iterator();
    }

    // Method 9
    // Step 6: Inserts the specified element at the tail of
    // this queue if possible to do so immediately without
    // exceeding the queue's capacity

    // Method 10
    public boolean offer(E e)
    {
        // Return true upon success and false
        // if this queue is full else return false
        return delayQueue.offer(e);
    }

    // Step 7: Inserts the specified element into delay
    // queue
    public boolean offer(E e, long timeout, TimeUnit unit)
        throws InterruptedException
    {
        return delayQueue.offer(e, timeout, unit);
    }

    // Method 11
    // Step 8: Retrieve but does not remove the head
    // of this queue
    public E peek()
    {
        // Or simply returns null if this queue is empty
        return delayQueue.peek();
    }

    // Step 8(a): Retrieves and removes the head of this
    // queue
    public E poll()
    {

        // Or simply returns null if this queue is empty.
        return delayQueue.poll();
    }

    // Step 8(b): Retrieves and removes the head of queue
    // waiting if necessary untilan element with an
    // expired delay is available on this queue
    public E poll(long timeout, TimeUnit unit)
        throws InterruptedException
    {
        return delayQueue.poll(timeout, unit);
    }

    // Method 12
    // Step 9: Insert the specified element into delay queue
    public void put(E e) throws InterruptedException
    {
        delayQueue.put(e);
    }

    // Method 13
    public int remainingCapacity()
    {
        // Remember : Always returns Integer.MAX_VALUE
        // because a DelayQueue is not capacity constrained
        return delayQueue.remainingCapacity();
    }

    // Step 10: Removes a single instance of the specified
    // element from this queue, if it is present
    public boolean remove(Object o)
    {
        return delayQueue.remove(o);
    }
    public int size() {
      return delayQueue.size();
    }
    // Retrieves and removes the head of this queue, waiting
    // if necessary until an element with an expired delay
    // is available on this queue.

    public E take() throws InterruptedException
    {
        // Returns an array containing all of the elements
        // in
        // this queue, in proper sequence.
        return delayQueue.take();
    }

    public Object[] toArray()
    {
        // Returns an array containing all elements in queue

        return delayQueue.toArray();
    }

    // The runtime type of the returned array is
    // that of the specified array
    public <T> T[] toArray(T[] a)
    {
        return delayQueue.toArray(a);
    }

    // Class
    static class DelayObjects implements Delayed {
        // Member variable of class
        public long time;

        // Member function of class
        public DelayObjects()
        {
            getDelay(TimeUnit.MILLISECONDS);
        }

        // Overriding using compareTo() method
        @Override public int compareTo(Delayed o)
        {
            if (this.time < ((DelayObjects)o).time)
                return -1;
            else if (this.time > ((DelayObjects)o).time)
                return 1;
            return 0;
        }

        @Override public long getDelay(TimeUnit unit)
        {
            time = System.currentTimeMillis();
            return time;
        }
    }

    // Main driver method
    public static void main(String[] args)
        throws InterruptedException
    {
        // Creating object of class- DelayQueueImpl
        DelayQueueImpl<DelayObjects> arrayBlockingQueue
            = new DelayQueueImpl<DelayObjects>();

        // Adding custom inputs
        DelayObjects delayObject1 = new DelayObjects();
        Thread.sleep(100);
        DelayObjects delayObject2 = new DelayObjects();
        Thread.sleep(100);
        DelayObjects delayObject3 = new DelayObjects();
        Thread.sleep(100);
        DelayObjects delayObject4 = new DelayObjects();
        Thread.sleep(100);
        DelayObjects delayObject5 = new DelayObjects();

        // Try block to check exceptions
        try {
            arrayBlockingQueue.put(delayObject1);
            arrayBlockingQueue.put(delayObject2);
            arrayBlockingQueue.put(delayObject3);
        }

        // Catch block to handle exceptions if occurs
        catch (InterruptedException e) {
            // Print the line number where exception occurred
            e.printStackTrace();
        }

        // Adding objects to above queue
        arrayBlockingQueue.add(delayObject4);
        arrayBlockingQueue.add(delayObject5);

        // Display message
        System.out.print(
            "Delaytimes of the DelayQueue is           : ");

        // iterator to traverse over collection
        Iterator<DelayObjects> itr
            = arrayBlockingQueue.iterator();

        // Condition check using hasNext()
        while (itr.hasNext()) {
            // Print elements
            System.out.print(itr.next().time + "\t");
        }

        // New line
        System.out.println();

        // Using offr() method over objects
        arrayBlockingQueue.offer(new DelayObjects());
        arrayBlockingQueue.offer(new DelayObjects());

        // Print and Display messages to showcase
        // implementation of DelayQueue API
        System.out.println(
            "Element time of the DelayQueue by peeking :  "
            + arrayBlockingQueue.peek().time);

        System.out.println(
            "Remaining capacity                         : "
            + arrayBlockingQueue.remainingCapacity());

        System.out.println(
            "DelayObject1 removed ?                    : "
            + arrayBlockingQueue.remove(delayObject1));

        System.out.println(
            "DelayQueue contains DelayObject2 ?        : "
            + arrayBlockingQueue.contains(delayObject2));

        System.out.println(
            "hash DelayQueue contains DelayObject3 ?   : "
            + arrayBlockingQueue.contains(delayObject3));

        System.out.println(
            "Size of the ArrayBlocingQueue             : "
            + arrayBlockingQueue.size());
    }
}
```

****Output**

```
Delaytimes of the DelayQueue is           : 1626870778483    1626870778583    1626870778683    1626870778786    1626870778886    
Element time of the DelayQueue by peeking :  1626870778483
Remaining capacity                         : 2147483647
DelayObject1 removed ?                    : true
DelayQueue contains DelayObject2 ?        : true
hash DelayQueue contains DelayObject3 ?   : true
Size of the ArrayBlocingQueue             : 6
```**