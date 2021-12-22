# Java 中的 ConcurrentSkipListSet remove()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-remove-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-remove-method-in-java/)

java . util . concurrentSkiplistset . remove()方法是 Java 中的一个内置函数，如果元素存在于这个集合中，它将被用来移除该元素。

**语法:**

```java
ConcurrentSkipListSet.remove(Object o)

```

**参数:**该功能接受单个参数 *o* ，即要移除的对象。

**返回值:**该函数在成功移除对象时返回真布尔值，否则返回假。

下面的程序说明了 ConcurrentSkipListSet.remove()方法:

**程序 1:** 集合中存在要移除的元素。

```java
// Java Program Demonstrate remove()
// method of ConcurrentSkipListSet

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetRemoveExample1 {
    public static void main(String[] args)
    {
        // Initializing the set
        ConcurrentSkipListSet<Integer> set = 
                         new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 1; i <= 5; i++)
            set.add(i);

        // Printing the elements of the set
        System.out.println("The elements in the set are:");
        for (Integer i : set)
            System.out.print(i + " ");

        // remove() method will remove the specified
        // element from the set
        set.remove(1);
        set.remove(5);

        // Printing the elements of the set
        System.out.println("\nRemaining elements in set : ");
        for (Integer i : set)
            System.out.print(i + " ");
    }
}
```

**输出:**

```java
The elements in the set are:
1 2 3 4 5 
Remaining elements in set : 
2 3 4

```

**程序 2:** 要移除的元素不在集合中。

```java
// Java Program Demonstrate remove()
// method of ConcurrentSkipListSet

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetRemoveExample2 {
    public static void main(String[] args)
    {
        // Initializing the set
        ConcurrentSkipListSet<Integer> set =
                       new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 15; i++)
            set.add(i);

        // Printing the elements of the set
        System.out.println("The elements in the set are:");
        for (Integer i : set)
            System.out.print(i + " ");

        // remove() method will remove the specified
        // element from the set
        set.remove(1);
        set.remove(5);

        // Printing the elements of the set
        System.out.println("\nRemaining elements in set : ");
        for (Integer i : set)
            System.out.print(i + " ");
    }
}
```

**输出:**

```java
The elements in the set are:
10 11 12 13 14 15 
Remaining elements in set : 
10 11 12 13 14 15

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # remove-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#remove-java.lang.Object-)