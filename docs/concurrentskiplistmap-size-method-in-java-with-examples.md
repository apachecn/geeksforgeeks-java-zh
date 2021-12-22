# Java 中的 ConcurrentSkipListMap size()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-size-method-in-java-with-examples/)

**java . util . concurrentskiplistmap**的 **size()** 方法是 Java 中的一个内置函数，它返回映射到这个映射的键的数量。size()方法不是常数时间操作。以防地图包含多个整数。MAX_VALUE 元素，则返回映射的最大值。

**语法:**

```java
public int size()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回该地图中元素的个数。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java Program Demonstrate size()
// method of ConcurrentSkipListMap

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the map
        ConcurrentSkipListMap<Integer, Integer>
            mpp = new ConcurrentSkipListMap<Integer,
                                            Integer>();

        // Adding elements to this map
        for (int i = 1; i <= 5; i++)
            mpp.put(i, i);

        // print size of map
        System.out.println(mpp.size());
    }
}
```

**输出:**

```java
5

```

**程序二:**

```java
// Java Program Demonstrate size()
// method of ConcurrentSkipListMap

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the map
        ConcurrentSkipListMap<Integer, Integer>
            mpp = new ConcurrentSkipListMap<Integer,
                                            Integer>();

        // Adding elements to this map
        for (int i = 1; i <= 15; i++)
            mpp.put(i, i);

        // print size of map
        System.out.println(mpp.size());
    }
}
```

**输出:**

```java
15

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistmap . html # size–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListMap.html#size--)