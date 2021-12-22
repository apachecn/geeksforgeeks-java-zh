# Java 中的 ConcurrentSkipListSet 比较器()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-comparator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistset-comparator-method-in-java-with-examples/)

java . util . concurrentskiplistset 的**比较器()**方法是 Java 中的一个内置函数，它返回用于给定集合中元素排序的比较器。如果使用自然排序，则返回 null。

**语法:**

```java
public Comparator<E> comparator()

```

这里 E 是类型参数，即集合维护的元素类型。

**返回值:**函数返回用于给定集合中元素排序的比较器，如果使用自然排序，则返回 null。

下面给出的程序说明了 concurrentskiplistset . comparator()方法:

**程序 1:**

```java
// Java program to demonstrate comparator()
// method of ConcurrentSkipListSet

import java.util.concurrent.*;

class ConcurrentSkipListSetcomparatorExample1 {
    public static void main(String[] args)
    {
        // Creating first set object
        ConcurrentSkipListSet<Integer> set1
            = new ConcurrentSkipListSet<Integer>();

        // Creating second set object
        ConcurrentSkipListSet<Integer> set2
            = new ConcurrentSkipListSet<Integer>();

        // Adding elements to first set
        set1.add(30);
        set1.add(5);
        set1.add(50);
        set1.add(20);

        // Ordering the elements in descending order
        set2 = (ConcurrentSkipListSet<Integer>)
                   set1.descendingSet();

        // Displaying the contents of the set1
        System.out.println("Contents of the set1: "
                           + set1);

        // Displaying the contents of the set2
        System.out.println("Contents of the set2: "
                           + set2);

        // Retrieving the comparator
        // used for ordering of elements
        System.out.println("The comparator"
                           + " used in the set:\n"
                           + set2.comparator());
    }
}
```

**Output:**

```java
Contents of the set1: [5, 20, 30, 50]
Contents of the set2: [50, 30, 20, 5]
The comparator used in the set:
java.util.Collections$ReverseComparator@74a14482

```

**程序 2:**

```java
// Java program to demonstrate comparator()
// method of ConcurrentSkipListSet

import java.util.concurrent.*;

class ConcurrentSkipListSetcomparatorExample2 {
    public static void main(String[] args)
    {
        // Creating first set object
        ConcurrentSkipListSet<Integer> set1
            = new ConcurrentSkipListSet<Integer>();

        // Adding elements to first set
        set1.add(30);
        set1.add(5);
        set1.add(50);
        set1.add(20);

        // Displaying the contents of the set1
        System.out.println("Contents of the set1: "
                           + set1);

        // Retrieving the comparator
        // used for ordering of elements
        System.out.println("The comparator used in the set: "
                           + set1.comparator());
    }
}
```

**Output:**

```java
Contents of the set1: [5, 20, 30, 50]
The comparator used in the set: null

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html #比较器–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#comparator--)