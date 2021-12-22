# Java 中的 ConcurrentSkipListSet 下行 terator()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-dependingiterator-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-descendingiterator-method-in-java/)

**java . util . concurrentskiplistset**的**dependingiterator()**方法是 Java 中的内置函数，用于以*降序*返回该集合中元素的迭代器。

**语法:**

```java
ConcurrentSkipListSet.descendingIterator()
```

**返回值:**函数以降序返回该集合中元素的迭代器。

下面的程序说明了 ConcurrentSkipListSet .下行畸胎()方法:

**程序 1:**

```java
// Java Program Demonstrate descendingIterator()
// method of ConcurrentSkipListSet 

import java.util.Iterator;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetIteratorExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<String>
            set = new ConcurrentSkipListSet<String>();

        // Adding elements to this set
        set.add("Gfg");
        set.add("is");
        set.add("fun!!");

        // Returns an iterator over the elements
        Iterator<String> iterator = set.descendingIterator();

        // Printing the elements of the set
        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");
    }
}
```

**输出:**

```java
is fun!! Gfg

```

**程序二:**

```java
// Java Program Demonstrate descendingIterator()
// method of ConcurrentSkipListSet 

import java.util.Iterator;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetIteratorExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        set.add(10);
        set.add(15);
        set.add(20);
        set.add(25);

        // Returns an iterator over the elements
        Iterator<Integer> iterator = set.descendingIterator();

        // Printing the elements of the set
        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");
    }
}
```

**输出:**

```java
25 20 15 10

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # DecendingTerrar–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#descendingIterator--)