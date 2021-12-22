# Java 中的 ConcurrentSkipListSet pollsfirst()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-poll first-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-pollfirst-method-in-java/)

**java . util . concurrentskiplistset**的**pollsfirst()**方法是 Java 中的一个内置函数，它返回检索并移除第一个(最低的)元素，如果这个集合为空，则返回 null。

**语法:**

```java
public E pollFirst()
```

**返回值:**函数返回检索并移除第一个(最低的)元素，如果该集合为空，则返回 null。

下面的程序说明了 concurrentskiplistset . pollsfirst()方法:

**程序 1:**

```java
// Java program to demonstrate pollFirst()
// method of ConcurrentSkipListSet

import java.util.concurrent.*;

class ConcurrentSkipListSetpollFirstExample1 {
    public static void main(String[] args)
    {
        // Creating a set object
        ConcurrentSkipListSet<Integer> 
Lset = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 50; i += 10)
            Lset.add(i);

        // Printing the content of the set
        System.out.println("Contents of the set: " + Lset);

        // Retrieving and removing first element of the set
        System.out.println("The first element of the set: " 
+ Lset.pollFirst());

        // Printing the content of the set after pollFirst()
        System.out.println("Contents of the set after pollFirst: " 
+ Lset);
    }
}
```

**Output:**

```java
Contents of the set: [10, 20, 30, 40, 50]
The first element of the set: 10
Contents of the set after pollFirst: [20, 30, 40, 50]

```

**程序 2:**

```java
// Java program to demonstrate pollFirst()
// method of ConcurrentSkipListSet

import java.util.concurrent.*;

class ConcurrentSkipListSetpollFirstExample2 {
    public static void main(String[] args)
    {
        // Creating a set object
        ConcurrentSkipListSet<Integer> 
Lset = new ConcurrentSkipListSet<Integer>();

        // Printing the content of the set
        System.out.println("Contents of the set: " + Lset);

        // Retrieving and removing first element of the set
        System.out.println("The first element of the set: " 
+ Lset.pollFirst());
    }
}
```

**Output:**

```java
Contents of the set: []
The first element of the set: null

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # pollsfirst–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#pollFirst--)