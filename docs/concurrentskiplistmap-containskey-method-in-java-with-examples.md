# 在 Java 中 ConcurrentSkipListMap contains key()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-contains key-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-containskey-method-in-java-with-examples/)

**[java . util . concurrentskiplistmap](https://www.geeksforgeeks.org/concurrentskiplistset-in-java-with-examples/)**的 **containsKey()** 方法是 Java 中的一个内置函数，如果指定的元素出现在这个映射中，它将返回一个真布尔值，否则它将返回 false。

**语法:**

```
public boolean containsKey(Object ob)

```

**参数:**该函数接受单个强制参数 **ob** ，该参数指定要测试其在该地图中的存在的键。

**返回值:**如果该映射包含指定键的映射，则函数返回真。

下面的程序说明了上述方法:

**节目 1:**

```
// Java Program Demonstrate containsKey()
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

        // Checks if 9 is present in the map
        if (mpp.containsKey(9))
            System.out.println("9 is present"
                               + " in the mpp.");
        else
            System.out.println("9 is not present"
                               + " in the mpp.");
    }
}
```

**节目 2:**

```
// Java Program Demonstrate containsKey()
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

        // Checks if 4 is present in the map
        if (mpp.containsKey(4))
            System.out.println("4 is present"
                               + " in the mpp.");
        else
            System.out.println("4 is not present"
                               + " in the mpp.");
    }
}
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrentskiplistmap . html # contains key-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/ConcurrentSkipListMap.html#containsKey-java.lang.Object-)