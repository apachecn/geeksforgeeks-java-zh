# Java 中的 ConcurrentSkipListSet add()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-add-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-add-method-in-java/)

**java . util . concurrentSkiplistset . add()**方法是 Java 中的一个内置函数，用于在这个集合中插入一个元素。

**语法:**

```java
ConcurrentSkipListSet.add(E e)

```

**参数:**该函数接受单个参数 *e* ，即要插入的元素。

**返回值:**该函数返回一个真布尔值。

下面的程序说明了 ConcurrentSkipListSet.add()方法:

**程序 1:** 在集合中添加整数。

```java
// Java program to demonstrate add()
// method of ConcurrentSkipListSet

import java.util.concurrent.*;

class ConcurrentSkipListSetAddExample1 {
    public static void main(String[] args)
    {
        // Creating a set object
        ConcurrentSkipListSet<Integer> Lset = 
                  new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 50; i += 10)
            Lset.add(i);

        // Printing elements of the set
        System.out.println("The set contains: ");
        for (Integer i : Lset)
            System.out.print(i + " ");
    }
}
```

**输出:**

```java
The set contains: 
10 20 30 40 50

```

**程序 2:** 在集合中添加字符串。

```java
// Java program to demonstrate add()
// method of ConcurrentSkipListSet

import java.util.concurrent.*;

class ConcurrentSkipListSetAddExample2 {
    public static void main(String[] args)
    {
        // Creating a set object
        ConcurrentSkipListSet<String> Lset = 
                     new ConcurrentSkipListSet<String>();

        // Adding elements to this set
        Lset.add("alex");
        Lset.add("bob");
        Lset.add("chuck");
        Lset.add("drake");
        Lset.add("eric");

        // Printing elements of the set
        System.out.println("The set contains: ");
        for (String i : Lset)
            System.out.print(i + " ");
    }
}
```

**输出:**

```java
The set contains: 
alex bob chuck drake eric

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrentskiplistset . html # add(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#add(E))