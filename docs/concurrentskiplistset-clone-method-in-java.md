# Java 中的 ConcurrentSkipListSet clone()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-clone-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-clone-method-in-java/)

**java . util . ConcurrentSkipListSet**的 **clone()** 方法是 Java 中的一个内置函数，它返回这个 ConcurrentSkipListSet 实例的一个浅层副本。

**语法:**

```java
ConcurrentSkipListSet.clone()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回一个 ConcurrentSkipListSet 的浅拷贝。

下面的程序说明了 ConcurrentSkipListSet.clone()方法:

**程序 1:**

```java
// Java Program Demonstrate clone()
// method of ConcurrentSkipListSet
import java.util.concurrent.*;

class ConcurrentSkipListSetCloneExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 15; i++)
            set.add(i);

        // Printing elements of the set
        System.out.println("The set contains: " + set);

        // Cloning the ConcurrentSkipListSet
        ConcurrentSkipListSet<Integer> clone_set = set.clone();

        // Adding elements to the clone set
        clone_set.add(16);

        // Printing elements of the clone set
        System.out.println("The clone set contains: " + clone_set);
    }
}
```

**输出:**

```java
The set contains: [10, 11, 12, 13, 14, 15]
The clone set contains: [10, 11, 12, 13, 14, 15, 16]

```

**程序二:**

```java
// Java Program Demonstrate clone()
// method of ConcurrentSkipListSet */
import java.util.concurrent.*;

class ConcurrentSkipListSetCloneExample2 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<String>
            set = new ConcurrentSkipListSet<String>();

        // Adding elements to this set
        set.add("Gfg");
        set.add("is");
        set.add("fun");

        // Printing elements of the set
        System.out.println("The set contains: " + set);

        // Cloning the ConcurrentSkipListSet
        ConcurrentSkipListSet<String> clone_set = set.clone();

        // Adding elements to the clone set
        clone_set.add("site");

        // Printing elements of the clone set
        System.out.println("The clone set contains: " + clone_set);
    }
}
```

**输出:**

```java
The set contains: [Gfg, fun, is]
The clone set contains: [Gfg, fun, is, site]

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrentskiplistset . html # clone()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#clone())