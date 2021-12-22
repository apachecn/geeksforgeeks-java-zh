# Java 中的 ConcurrentSkipListMap clear()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-clear-method-in-java-with-examples/)

**java . util . concurrentskiplistmap**的 **clear()** 方法是 Java 中的一个内置函数，它删除了该映射中的所有映射。这意味着地图中的所有元素都被移除，并返回一个空地图。

**语法:**

```
public void clear()

```

**参数:**函数不接受任何参数。

**返回值:**该函数从此映射中移除所有映射。

下面的程序说明了上述方法:

**程序 1:**

```
// Java Program Demonstrate clear()
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

        // print original map
        System.out.println("map elements are: "
                           + mpp);

        mpp.clear();

        // after clear() operation
        System.out.println("after clear the map is: "
                           + mpp);
    }
}
```

**输出:**

```
map elements are: {1=1, 2=2, 3=3, 4=4, 5=5}
after clear the map is: {}

```

**程序二:**

```
// Java Program Demonstrate clear()
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
        for (int i = 1; i <= 10; i++)
            mpp.put(i, i);

        // print original map
        System.out.println("map elements are: "
                           + mpp);

        mpp.clear();

        // after clear() operation
        System.out.println("after clear the map is: "
                           + mpp);
    }
}
```

**输出:**

```
map elements are: {1=1, 2=2, 3=3, 4=4, 5=5, 6=6, 7=7, 8=8, 9=9, 10=10}
after clear the map is: {}

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistmap . html # clear–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListMap.html#clear--)