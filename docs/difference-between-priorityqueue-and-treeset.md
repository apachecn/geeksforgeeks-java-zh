# 优先级队列和树集的区别

> 原文:[https://www . geeksforgeeks . org/priority queue-and-treeset 之间的差异/](https://www.geeksforgeeks.org/difference-between-priorityqueue-and-treeset/)

优先级队列和树集合都是在[集合框架中定义的类。](https://www.geeksforgeeks.org/collections-in-java-2/)在本文中，我们将学习 PriorityQueue 和 TreeSet 的区别。优先级队列是[队列](https://www.geeksforgeeks.org/queue-interface-java/)接口的实现，树集合是[集合](https://www.geeksforgeeks.org/set-in-java/)接口的实现。他们之间存在一些差异。因此，我们试图列出优先级队列和树集之间的区别。

**1。** [**优先级队列**](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/) **:** 优先级队列用于根据优先级处理对象。众所周知，一个 [队列](https://www.geeksforgeeks.org/queue-interface-java/) 遵循先进先出算法，但有时队列的元素需要按照优先级进行处理，也就是优先级队列开始发挥作用的时候。优先级队列基于优先级堆。优先级队列的元素根据自然顺序进行排序，或者由队列构建时提供的比较器进行排序，具体取决于使用的构造函数。

**优先权队列演示:**

## 【Java】

```
// Java program to demonstrate the
// working of PriorityQueue
import java.util.*;

class PriorityQueueDemo {

    // Main Method
    public static void main(String args[])
    {
        // Creating empty priority queue
        PriorityQueue<String> pQueue
            = new PriorityQueue<>();

        // Adding elements to the pQueue using add()
        pQueue.add("Geeks");
        pQueue.add("For");
        pQueue.add("Geeks");

        // Printing the top element of PriorityQueue
        System.out.println(pQueue.peek());

        // Printing the top element and removing it
        // from the PriorityQueue container
        System.out.println(pQueue.poll());

        // Printing the top element again
        System.out.println(pQueue.peek());
    }
}
```

输出

```
For
For
Geeks

```