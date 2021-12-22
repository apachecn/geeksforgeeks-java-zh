# Java 中的 ConcurrentSkipListSet equals()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-equals-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-equals-method-in-java/)

java . util . concurrentSkiplistset 的 equals()方法是 Java 中的一个内置函数，它将指定的对象与该集合进行比较以获得相等性。如果指定的对象也是集合，则返回真。如果两个集合满足以下所有条件，则称它们相等:

*   These two sets have the same size.
*   Each member of the specified collection is contained in this collection.

这个定义确保了 equals 方法可以在 set 接口的不同实现中正常工作。

**语法:**

```java
ConcurrentSkipListSet.equals(Object o)
```

**参数:**该函数返回单个参数 *o* ，即要与该集合进行相等比较的对象

**返回值:**函数返回布尔值。如果指定的对象等于该集合，则返回 true，否则返回 false。

下面的程序说明了 ConcurrentSkipListSet.equals()方法:

**程序 1:** 在本例中，两个集合相等。

```java
// Java Program Demonstrate equals()
// method of ConcurrentSkipListSet

import java.util.NavigableSet;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetEqualsExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        set.add(10);
        set.add(35);
        set.add(20);
        set.add(25);

        // Creating a descending set object
        NavigableSet<Integer> des_set = set.descendingSet();

        // Checking if the set and des
        if (set.equals(des_set))
            System.out.println("Both the sets are equal");
        else
            System.out.println("Both the sets are not equal");

        // Printing the elements of the set
        System.out.println("Contents of the set: " + set);

        // Printing the elements of the descending set
        System.out.println("Contents of the descending set: " + 
                                                      des_set);
    }
}
```

**输出:**

```java
Both the sets are equal
Contents of the set: [10, 20, 25, 35]
Contents of the descending set: [35, 25, 20, 10]

```

**程序 2:** 在本例中两个集合不相等

```java
// Java Program Demonstrate equals()
// method of ConcurrentSkipListSet

import java.util.NavigableSet;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetEqualsExample2 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set1 = new ConcurrentSkipListSet<Integer>();

        ConcurrentSkipListSet<Integer>
            set2 = new ConcurrentSkipListSet<Integer>();

        // Adding elements to first set
        set1.add(10);
        set1.add(35);
        set1.add(20);
        set1.add(25);

        // Adding elements to second set
        set2.add(35);
        set2.add(20);
        set2.add(25);

        // Checking if the set and des
        if (set1.equals(set2))
            System.out.println("Both the sets are equal");
        else
            System.out.println("Both the sets are not equal");

        // Printing the elements of the set
        System.out.println("Contents of the first set: " + 
                                                      set1);

        // Printing the elements of the descending set
        System.out.println("Contents of the second set: " + 
                                                      set2);
    }
}
```

**输出:**

```java
Both the sets are not equal
Contents of the first set: [10, 20, 25, 35]
Contents of the second set: [20, 25, 35]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # equals-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#equals-java.lang.Object-)