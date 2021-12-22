# Java 中的 ConcurrentSkipListMap ceiling key()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-ceiling key-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-ceilingkey-method-in-java-with-examples/)

**java . util . concurrentskiplistmap**的 **ceilingKey()** 方法是 Java 中的一个内置函数，它返回大于或等于给定键的最小键。如果没有这样的值，则返回 null。当没有键时，该方法引发 NullPointerException。

**语法:**

```
public K ceilingKey(K key)

```

**参数:**该功能接受单个强制参数**键**，指定该键。

**返回值:**该函数返回大于或等于键的最小键，如果没有这样的键，则返回空。

**异常:**该方法抛出两种类型的异常:

*   **ClassCastException:** 如果指定的关键点无法与当前地图中的关键点进行比较，并且
*   **NullPointRexception:**如果指定的键为空。

下面的程序说明了上面的方法:
**程序 1:**

```
// Java program to demonstrate
// ceilingkey method in java

import java.util.concurrent.ConcurrentSkipListMap;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the set
        // using ConcurrentSkipListMap()
        ConcurrentSkipListMap<Integer, Integer>
            mpp = new ConcurrentSkipListMap<Integer,
                                            Integer>();

        // Adding elements to this set
        mpp.put(1, 1);
        mpp.put(5, 2);
        mpp.put(2, 7);

        // Printing the ConcurrentSkipListMap
        // Always in ascending order

        System.out.println("Map: "
                           + mpp);

        System.out.println("key greater than or equal 3: "
                           + mpp.ceilingKey(3));

        System.out.println("key greater than or equal 2: "
                           + mpp.ceilingKey(2));
    }
}
```

**Output:**

```
Map: {1=1, 2=7, 5=2}
key greater than or equal 3: 5
key greater than or equal 2: 2

```

**程序 2:**

```
// Java program to demonstrate
// ceilingkey method in java
import java.util.concurrent.ConcurrentSkipListMap;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the set
        // using ConcurrentSkipListMap()
        ConcurrentSkipListMap<Integer, Integer>
            mpp = new ConcurrentSkipListMap<Integer,
                                            Integer>();

        // Adding elements to this set
        mpp.put(11, 1);
        mpp.put(51, 42);
        mpp.put(92, 7);

        // Printing the ConcurrentSkipListMap
        // Always in ascending order

        System.out.println("Map: "
                           + mpp);

        System.out.println("key greater than or equal 11: "
                           + mpp.ceilingKey(11));

        System.out.println("key greater than or equal 51: "
                           + mpp.ceilingKey(51));
    }
}
```

**Output:**

```
Map: {11=1, 51=42, 92=7}
key greater than or equal 11: 11
key greater than or equal 51: 51

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistmap . html # ceilingKey-K-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListMap.html#ceilingKey-K-)