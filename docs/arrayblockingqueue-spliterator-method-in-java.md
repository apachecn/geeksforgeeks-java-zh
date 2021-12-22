# Java 中的 ArrayBlockingQueue spliterator()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-spliterator-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-spliterator-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)的**拆分器()**方法在 ArrayBlockingQueue 的元素上返回一个[拆分器](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)。返回的迭代器弱一致。在 Java 8 中，拆分器可以与 Streams 一起使用。分割器也可以单独和批量遍历元素。
**语法:**

```
public Spliterator spliterator()
```

**返回值:**这个方法在 ArrayBlockingQueue 中的元素上返回一个拆分器。
下面的程序说明了 ArrayBlockingQueue 类的 spliterator()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate spliterator()
// method of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;
import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacityOfQueue = 7;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> Queue
            = new ArrayBlockingQueue<Integer>(capacityOfQueue);

        // Add element to ArrayBlockingQueue
        Queue.add(22);
        Queue.add(34);
        Queue.add(45);
        Queue.add(67);

        // create Spliterator of Queue
        // using spliterator() method
        Spliterator<Integer> numbers = Queue.spliterator();

        // getExactSize of Spliterator
        System.out.println("Size of Spliterator : "
                           + numbers.estimateSize());

        System.out.println("list of Numbers:");
        // forEachRemaining method of Spliterator
        numbers.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**Output:** 

```
Size of Spliterator : 4
list of Numbers:
22
34
45
67
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate spliterator()
// method of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;
import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacityOfQueue = 7;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<String> QueueOfStrings
            = new ArrayBlockingQueue<String>(capacityOfQueue);

        // Add element to ArrayBlockingQueue
        QueueOfStrings.add("India");
        QueueOfStrings.add("Pakistan");
        QueueOfStrings.add("England");
        QueueOfStrings.add("China");
        QueueOfStrings.add("UAE");
        QueueOfStrings.add("Spain");

        // create Spliterator of QueueOfStrings
        // using spliterator() method
        Spliterator<String>
            listOfStrings = QueueOfStrings.spliterator();

        // getExactSize of Spliterator
        System.out.println("Size of Spliterator : "
                           + listOfStrings.estimateSize());

        System.out.println("list of Country names:");

        // forEachRemaining method of Spliterator
        listOfStrings.forEachRemaining((str) -> print(str));
    }
    public static void print(String str)
    {
        System.out.println("Value = " + str);
    }
}
```

**Output:** 

```
Size of Spliterator : 6
list of Country names:
Value = India
Value = Pakistan
Value = England
Value = China
Value = UAE
Value = Spain
```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/arrayblockingqueue . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#spliterator--)