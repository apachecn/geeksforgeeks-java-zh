# Java 中的 ConcurrentSkipListSet isEmpty()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-isempty-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-isempty-method-in-java/)

java . util . concurrentSkiplistset . isempty()方法是 Java 中的内置函数，用于检查该集合是否为空。

**语法:**

```java
ConcurrentSkipListSet.isEmpty()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回一个布尔值。如果 ConcurrentSkipListSet 为空，则返回 true，否则返回 false。

下面的程序说明了 ConcurrentSkipListSet。IsEmpty()方法:

**程序 1:** 在这个程序中，ConcurrentSkipListSet 是非空的。

```java
// Java Program to demonstrate isEmpty()
// method of ConcurrentSkipListSet() 

import java.util.concurrent.*;

class ConcurrentSkipListSetIsEmptyExample1 {
    public static void main(String[] args)
    {
        // Creating a set object
        ConcurrentSkipListSet<Integer> Lset = 
                   new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 50; i += 10)
            Lset.add(i);

        // Checks if this set is empty or not
        if (Lset.isEmpty())
            System.out.println("The set is empty.");
        else
            System.out.println("The set is non-empty.");
    }
}
```

**输出:**

```java
The set is non-empty.

```

**程序 2:** 在该程序中，ConcurrentSkipListSet 为空。

```java
// Java program to demonstrate isEmpty()
// method of ConcurrentSkipListSet() 

import java.util.concurrent.*;

class ConcurrentSkipListSetIsEmptyExample2 {
    public static void main(String[] args)
    {
        // Creating a set object
        ConcurrentSkipListSet<Integer> Lset = 
                       new ConcurrentSkipListSet<Integer>();

        // Checks if this set is empty or not
        if (Lset.isEmpty())
            System.out.println("The set is empty.");
        else
            System.out.println("The set is non-empty.");
    }
}
```

**输出:**

```java
The set is empty.

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrentskiplistset . html # add(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#add(E))