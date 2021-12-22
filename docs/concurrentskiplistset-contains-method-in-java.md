# 在 Java 中 ConcurrentSkipListSet 包含()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-contains-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-contains-method-in-java/)

**java . util . concurrentskiplistset**的 **contains()** 方法是 Java 中的内置函数，如果该集合中存在指定的元素，则返回真布尔值，否则返回假值。

**语法:**

```
ConcurrentSkipListSet.contains(Object o)
```

**参数:**该功能接受单个参数 *o* ，即检查该组中是否存在该参数。

**返回值:**该函数返回一个布尔值。如果该集合中存在指定的元素，则返回真，否则返回假。

下面的程序说明了 ConcurrentSkipListSet.contains()方法:

**程序 1:**

```
// Java Program Demonstrate contains()
// method of ConcurrentSkipListSet

import java.util.concurrent.*;

class ConcurrentSkipListSetContainsExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 15; i++)
            set.add(i);

        // Checks if 9 is present in the set
        if (set.contains(9))
            System.out.println("9 is present in the set.");
        else
            System.out.println("9 is not present in the set.");
    }
}
```

**输出:**

```
9 is not present in the set.

```

**程序二:**

```
// Java Program Demonstrate contains()
// method of ConcurrentSkipListSet */

import java.util.concurrent.*;

class ConcurrentSkipListSetContainsExample2 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<String>
            set = new ConcurrentSkipListSet<String>();

        // Adding elements to this set
        set.add("Gfg");
        set.add("is");
        set.add("fun");

        // Checks if Gfg is present in the set
        if (set.contains("Gfg"))
            System.out.println("Gfg is present in the set.");
        else
            System.out.println("Gfg is not present in the set.");
    }
}
```

**输出:**

```
Gfg is present in the set.

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # contains-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#contains-java.lang.Object-)