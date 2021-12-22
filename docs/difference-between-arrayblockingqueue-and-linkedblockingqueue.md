# 【ArrayBlockingQueue 和 LinkedBlockingQueue 的区别

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue 和-linkedblockingqueue 之间的差异/](https://www.geeksforgeeks.org/difference-between-arrayblockingqueue-and-linkedblockingqueue/)

[Java Collection 中的 ArrayBlockingQueue](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/) 和 LinkedBlockingQueue 是[阻塞队列](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/)接口的常见实现。

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)**:**ArrayBlockingQueue 是 Java 中实现 **BlockingQueue** 接口的类。ArrayBlockingQueue 类及其迭代器实现集合和迭代器接口的所有可选方法。 ArrayBlockingQueue 是一个由数组支持的有界阻塞队列。这里，有界意味着队列的大小是有限且固定的。一旦创建，我们就不能增加或缩小队列的大小。如果我们试图将一个元素插入到一个完整的队列中，那么它将导致操作阻塞。类似地，如果我们试图从一个空队列中获取一个元素，那么操作也会被阻塞。ArrayBlockingQueue 按照****(先进先出)** 的顺序将队列中的元素存储在内部中。队列头部或前面的元素是该队列中所有元素中最早的元素。该队列尾部的元素是该队列所有元素中最新的元素。新元素总是被插入到队列的末尾或尾部，检索操作在队列的头部获取元素。**

**[**LinkedBlockingQueue**](https://www.geeksforgeeks.org/linkedblockingqueue-class-in-java/#:~:text=LinkedBlockingQueue%20is%20an%20optionally%2Dbounded,to%20the%20constructor%20of%20LinkedBlockingQueue.):**LinkedBlockingQueue 是 Java 中实现 BlockingQueue 接口的一个类。** **LinkedBlockingQueue 是一个**可选-** **有界的** 阻塞队列，由链接节点支持。这里，可选有界表示赋予 LinkedBlockingQueue 的容量是有界的，否则、将是无界的。容量可以作为参数提供给 LinkedBlockingQueue 的构造函数。容量，如果未指明，等于 **整数。MAX_VALUE** 。链接的阻塞队列类及其迭代器实现了集合和迭代器接口的所有可选方法。LinkedBlockingQueue 将队列中的元素以 **FIFO** **(先进先出)** 的顺序存储在内部中。队列头部或前面的元素是该队列中所有元素中最早的元素。这个队列尾部的元素是这个队列所有元素中最新的元素。新元素总是被插入到队列的末尾或尾部，检索操作在队列的头部获取元素。在大多数并发应用程序中，链接队列通常比基于阵列的队列具有更高的吞吐量，但可预测性较差。****

******【链锁队列演示】******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java program to demonstrate LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class LinkedBlockingQueueDemo {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacity = 15;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer> lbq
            = new LinkedBlockingQueue<Integer>(capacity);

        // add numbers
        lbq.add(1);
        lbq.add(2);
        lbq.add(3);

        // print queue
        System.out.println("LinkedBlockingQueue:" + lbq);
    }
}**
```

******Output**

```
LinkedBlockingQueue:[1, 2, 3]

```**** 

******阵列阻塞队列演示******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java program to demonstrate
// ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;

public class ArrayBlockingQueueDemo {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 15;

        // create object of ArrayBlockingQueue
        // using ArrayBlockingQueue(int initialCapacity)
        // constructor
        ArrayBlockingQueue<Integer> abq
            = new ArrayBlockingQueue<Integer>(capacity);

        // add numbers
        abq.add(1);
        abq.add(2);
        abq.add(3);

        // print queue
        System.out.println("ArrayBlockingQueue:" + abq);
    }
}**
```

******Output**

```
ArrayBlockingQueue:[1, 2, 3]

```**** 

****【ArrayBlockingQueue 和 LinkedBlockingQueue 的区别:****

<figure class="table">

| 

**数组块队列**

 | 

链接块队列

 |
| --- | --- |
| 它将元素存储在数组内部。 | 它将元素存储在链接节点的内部。 |
| [ArrayBlockingQueue](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/) 是有界的，这意味着大小在创建后永远不会改变。 | [LinkedBlockingQueue](https://www.geeksforgeeks.org/linkedblockingqueue-class-in-java/#:~:text=LinkedBlockingQueue%20is%20an%20optionally%2Dbounded,to%20the%20constructor%20of%20LinkedBlockingQueue.) 是可选有界的，这意味着如果需要，它可以可选地具有上限。如果没有指定上限，**整数。最大值**作为上限。 |
| 它的吞吐量低于链接节点队列。 | 它比基于阵列的队列具有更高的吞吐量。 |
| 它使用单锁双条件算法。这意味着生产者和消费者共享一个锁。 | 它使用两种锁队列算法，并且具有两种锁条件 putLock 和 takeLock，分别用于在队列中插入和移除元素。 |
| ArrayBlockingQueue 始终保存一个对象数组 | LinkedBlockingQueue 是一个链接节点，其对象包含三个对象字段。 |

</figure>