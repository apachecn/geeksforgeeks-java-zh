# Java 中的 ConcurrentSkipListSet size()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-size-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-size-method-in-java/)

**java . util . concurrentSkiplistset . size()**方法是 Java 中的一个内置函数，它给出了集合中存在的元素的总数。

**语法:**

```java
ConcurrentSkipListSet.size()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回队列中元素的个数。

下面的程序说明了 ConcurrentSkipListSet.size()方法:

**程序 1:**

```java
// Java Program Demonstrate size()
// method of ConcurrentSkipListSet

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetSizeExample1 {
    public static void main(String[] args)
    {
        // Initializing the set
        ConcurrentSkipListSet<Integer> set = 
                       new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 1; i <= 10; i++)
            set.add(i);

        // Printing the size of the set
        System.out.println("Number of elements in the set = "
                           + set.size());
        // Printing the elements
        System.out.println("set : " + set);
    }
}
```

**输出:**

```java
Number of elements in the set = 10
set : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

```

**程序二:**

```java
// Java Program Demonstrate size()
// method of ConcurrentSkipListSet

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetSizeExample2 {
    public static void main(String[] args)
    {
        // Initializing the set
        ConcurrentSkipListSet<String> set = 
                         new ConcurrentSkipListSet<String>();

        // Adding elements to this set
        set.add("A");
        set.add("B");
        set.add("C");
        set.add("D");
        set.add("E");

        // Printing the size of the set
        System.out.println("Number of elements in the set = "
                           + set.size());
        // Printing the elements
        System.out.println("set : " + set);
    }
}
```

**输出:**

```java
Number of elements in the set = 5
set : [A, B, C, D, E]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # size–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#size--)