# Java 中的 ConcurrentSkipListSet 下行 Set()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-descendingset-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-descendingset-method-in-java/)

**java . util . concurrentskiplistset**的**dependingset()**方法是 Java 中的一个内置函数，它返回这个集合中包含的元素的逆序视图。该集合支持降序集合，因此对该集合的更改会反映在降序集合中，反之亦然。

**语法:**

```java
ConcurrentSkipListSet.descendingSet()
```

**返回值:**该函数返回一个导航集，它是这个集合的逆序视图。

下面的程序说明了 ConcurrentSkipListSet。Set()方法:

**程序 1:**

```java
// Java Program Demonstrate descendingSet()
// method of ConcurrentSkipListSet */
import java.util.NavigableSet;
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
        set.add(35);
        set.add(20);
        set.add(25);

        // Printing the elements of the set
        System.out.println("Contents of the set: " + set);

        // Creating a descending set object
        NavigableSet<Integer> des_set = set.descendingSet();

        // Printing the elements of the descending set
        System.out.println("Contents of the descending set: " 
                                                  + des_set);
    }
}
```

**输出:**

```java
Contents of the set: [10, 20, 25, 35]
Contents of the descending set: [35, 25, 20, 10]

```

**程序 2:** 演示在下降集合中插入元素时原始集合发生变化的程序。

```java
// Java Program Demonstrate descendingSet()
// method of ConcurrentSkipListSet */
import java.util.NavigableSet;
import java.util.Iterator;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetIteratorExample2 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<String>
            set = new ConcurrentSkipListSet<String>();

        // Adding elements to this set
        set.add("bob");
        set.add("alex");
        set.add("eric");
        set.add("chuck");

        // Creating a descending object
        NavigableSet<String> des_set = set.descendingSet();

        // Adding elements to the descending set and also to the set
        des_set.add("drake");
        des_set.add("fred");

        // Printing the elements of the set
        System.out.println("Contents of the set: " + set);

        // Printing the elements of the descending set
        System.out.println("Contents of the descending set: " 
                                                  + des_set);
    }
}
```

**输出:**

```java
Contents of the set: [alex, bob, chuck, drake, eric, fred]
Contents of the descending set: [fred, eric, drake, chuck, bob, alex]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # descendingSet–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#descendingSet--)