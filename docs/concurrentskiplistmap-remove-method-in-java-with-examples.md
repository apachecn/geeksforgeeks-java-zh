# Java 中的 ConcurrentSkipListMap remove()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-remove-method-in-java-with-examples/)

**java . util . concurrentskiplistmap**的 **remove()** 方法是 Java 中的一个内置函数，它从该映射中删除指定键的映射。如果没有该特定键的映射，则方法返回 null。执行此方法后，地图的大小会减小。

**语法:**

```
ConcurrentSkipListMap.remove(Object ob)

```

**参数:**该函数接受单个强制参数 **ob** ，该参数指定要删除其映射的键。

**返回值:**该函数返回与指定键相关联的前一个值，如果该键没有映射，则返回空值。

下面的程序说明了上面的方法:

```
// Java Program Demonstrate remove()
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
        // remove() operation on the map
        mpp.remove(1);

        System.out.println("After remove(): " + mpp);
    }
}
```

**输出:**

```
After remove(): {2=2, 3=3, 4=4, 5=5}

```

**程序二:**

```
// Java Program Demonstrate remove()
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
        // remove() operation on the map
        mpp.remove(5);

        System.out.println("After remove(): " + mpp);
    }
}
```

**输出:**

```
After remove(): {1=1, 2=2, 3=3, 4=4}

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistmap . html # remove-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListMap.html#remove-java.lang.Object-)