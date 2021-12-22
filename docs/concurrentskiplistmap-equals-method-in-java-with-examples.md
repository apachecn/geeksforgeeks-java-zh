# Java 中的 ConcurrentSkipListMap equals()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-equals-method-in-java-with-examples/)

**java . util . concurrentskiplistmap**的 **equals()** 方法是 Java 中的一个内置函数，用于检查这个 Map 对象与指定对象的相等性。如果给定对象也是前一个对象的映射，并且这两个映射具有相同的映射，则方法返回 true。

**语法:**

```
public boolean equals(Object ob)

```

**参数:**该函数接受单个强制参数 **ob** ，该参数指定要与该地图进行相等比较的对象。

**返回值:**如果指定对象等于该地图，则函数返回真。

下面的程序说明了上述方法:

**程序 1:**

```
// Java Program Demonstrate equals()
// method of ConcurrentSkipListMap

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the map
        ConcurrentSkipListMap<Integer, Integer>
            mpp = new ConcurrentSkipListMap<Integer,
                                            Integer>();

        // adding elements in map
        for (int i = 1; i <= 5; i++)
            mpp.put(i, i);

        // equals operation on map
        System.out.println(mpp.equals(4));
    }
}
```

**输出:**

```
false

```

**程序二:**

```
// Java Program Demonstrate equals()
// method of ConcurrentSkipListMap

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the map
        ConcurrentSkipListMap<Integer, Integer>
            mpp = new ConcurrentSkipListMap<Integer,
                                            Integer>();

        // adding elements in map
        for (int i = 1; i <= 5; i++)
            mpp.put(i, i);

        // equals operation on map
        System.out.println(mpp.equals(3));
    }
}
```

**输出:**

```
false

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistmap . html # equals-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListMap.html#equals-java.lang.Object-)