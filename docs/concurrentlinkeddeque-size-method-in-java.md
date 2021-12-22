# Java 中的 concurrentlinkedequesize()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-size-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-size-method-in-java/)

Java 中[concurrentlinkedeque 类的 **size()** 方法用于查找 concurrentlinkedeque 容器中存在的元素数量。换句话说，这个方法告诉容器的当前容量。此方法返回的值是整型的，如果容器包含的元素多于整数的最大值，则此方法返回整数的最大值，即 integer。最大值。
**语法** :](https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/) 

```java
ConcurrentLinkedDeque.size()
```

**参数**:该方法不接受任何参数。
**返回值**:这个方法返回一个整数值，它是 ConcurrentLinkedDeque 容器的当前大小。
以下程序说明了并发链接请求的大小()方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate the
// size of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        // Create a ConcurrentLinkedDeque
        // using ConcurrentLinkedDeque() constructor
        ConcurrentLinkedDeque<Integer>
            cld = new ConcurrentLinkedDeque<Integer>();

        // Adding elements to the collection
        cld.addFirst(12);
        cld.addFirst(70);
        cld.addFirst(1009);
        cld.addFirst(475);

        // Displaying the ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Calculate size
        int size = cld.size();

        System.out.println("Size of the collection is: "
                           + size);
    }
}
```

**Output:** 

```java
ConcurrentLinkedDeque: [475, 1009, 70, 12]
Size of the collection is: 4
```

**注**:与 Java 中的其他集合不同，由于这些 decq 的异步性质，该方法不会在恒定时间内执行 ConcurrentLinkedDeque 的大小计算操作，并且在执行该方法的过程中大小可能会发生变化，在这种情况下返回的结果会不准确。这种方法在并发应用程序中通常不是很有用。
**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrentlinkedeque . html # size()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#size())