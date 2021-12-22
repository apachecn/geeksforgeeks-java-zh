# Java 中的 ConcurrentSkipListSet last()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-last-in-method-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-last-method-in-java/)

**java . util . concurrentskiplistset**的 **last()** 方法是 Java 中的一个内置函数，它返回当前在这个集合中的最后一个(最高的)元素。

**语法:**

```
public E last()
```

**返回值:**函数返回当前在这个集合中的最后一个(最高的)元素。

**异常:**如果该集合为空，函数抛出 NoSuchElementException。

下面的程序说明了 ConcurrentSkipListSet.last()方法:

**程序 1:**

```
// Java program to demonstrate last()
// method of ConcurrentSkipListSet

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetLastExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        set.add(78);
        set.add(64);
        set.add(12);
        set.add(45);
        set.add(8);

        // Printing the highest element of the set
        System.out.println("The highest element of the set: "
                           + set.last());
    }
}
```

**输出:**

```
The highest element of the set: 78

```

**程序 2:** 程序在最后()显示 NoSuchElementException。

```
// Java program to demonstrate last()
// method of ConcurrentSkipListSet

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetLastExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();
        try {
            // Printing the highest element of the set
            System.out.println("The highest element of the set: "
                               + set.last());
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Exception: java.util.NoSuchElementException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # last–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#last--)