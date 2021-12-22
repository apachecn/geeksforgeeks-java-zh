# 【ArrayBlockingQueue 和 ArrayDeque 的区别

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue 和-arraydeque 之间的差异/](https://www.geeksforgeeks.org/difference-between-arrayblockingqueue-and-arraydeque/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是 Java 中实现 BlockingQueue 接口的类。ArrayBlockingQueue 类及其迭代器实现了集合和迭代器接口的所有可选方法。ArrayBlockingQueue 是由数组支持的有界阻塞队列。这里，有界意味着队列的大小是有限且固定的。一旦创建，就不能增加或缩小队列的大小。如果试图将一个元素插入到一个完整的队列中，那么它将导致操作阻塞。同样，如果试图从空队列中获取一个元素，那么操作也会被阻止。ArrayBlockingQueue 按照(先进先出)的顺序在内部存储队列中的元素。队列头部或前面的元素是该队列中所有元素中最早的元素。这个队列尾部的元素是这个队列所有元素中最新的元素。新元素总是被插入到队列的末尾或尾部，检索操作在队列的头部获取元素。

**ArrayBlockingQueue 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;

public class ArrayBlockingQueueDemo {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 15;

        // create object of ArrayBlockingQueue
        // using ArrayBlockingQueue constructor
        ArrayBlockingQueue<Integer> abq
            = new ArrayBlockingQueue<Integer>(capacity);

        // add numbers
        abq.add(1);
        abq.add(2);
        abq.add(3);

        // print queue
        System.out.println("ArrayBlockingQueue:" + abq);
    }
}
```

**Output**

```
ArrayBlockingQueue:[1, 2, 3]

```

[**ArrayDeque**](https://www.geeksforgeeks.org/arraydeque-in-java/)是 Java 中一个同时实现 Queue 和 Deque 的类。它从两侧动态地重新调整大小。这是一种特殊的数组，它不断增长，允许用户在队列的两端添加或删除元素。又称 ***阵双端队列*** 或 ***阵甲板*** 。

少***ArrayDeque 的重要特征*** 如下:

*   ArrayDeque 没有容量限制，它们会根据需要增长以支持使用。
*   它们不是线程安全的，这意味着在没有外部同步的情况下，ArrayDeque 不支持多线程并发访问。
*   数组中禁止空元素。
*   ArrayDeque 类用作堆栈时可能比 Stack 更快。
*   当用作队列时，ArrayDeque 类可能比 LinkedList 更快。

**ArrayDeque 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate ArrayDeque

import java.util.*;

public class ArrayDequeDemo {

    public static void main(String[] args)
    {

        // Initializing an deque
        Deque<Integer> de_que = new ArrayDeque<Integer>(10);

        // add numbers
        de_que.add(10);
        de_que.add(20);
        de_que.add(30);

        // print queue
        System.out.println("ArrayDeque:" + de_que);
    }
}
```

**Output**

```
ArrayDeque:[10, 20, 30]

```

【ArrayBlockingQueue 和 ArrayDeque 的区别:

<figure class="table">

| **序列号** | **数组块队列** | 阵列 |
| --- | --- | --- |
| 1. | ArrayBlockingQueue 实现了阻塞队列接口。 | ArrayDeque 实现了 Deque 接口。 |
| 2. | 这是一个固定大小的数组队列。因此，一旦我们创建了阵列，我们就不能扩大和缩小阵列的大小。 | 这是一个可调整大小的数组队列。因此，我们可以扩大和缩小阵列的大小。 |
| 3. | 只能在队列的一侧添加或移除元素。 | 能够添加或删除队列两端的元素。 |
| 4.  | ArrayBlockingQueue 是线程安全的。 | ArrayDeque 不是线程安全的。 |
| 5. | ArrayBlockingQueue 类并不比 ArrayDeque 类快。 | ArrayDeque 类比 ArrayBlockingQueue 类更快。 |

</figure>