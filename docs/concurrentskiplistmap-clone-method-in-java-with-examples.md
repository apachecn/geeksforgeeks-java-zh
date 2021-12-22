# Java 中的 ConcurrentSkipListMap 克隆()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-clone-method-in-java-with-examples/)

**[java . util . ConcurrentSkipListMap](https://www.geeksforgeeks.org/concurrentskiplistset-in-java-with-examples/)**的 **clone()方法**是 Java 中的一个内置函数，它返回这个 ConcurrentSkipListMap 实例的一个浅拷贝。键和值本身不会被克隆。

**语法:**

```
ConcurrentSkipListMap.clone()

```

**参数:**函数不接受任何参数。

**参数:**该方法不接受任何参数。

**返回值:**函数返回这个 ConcurrentSkipListMap 的一个浅拷贝。

下面的程序说明了上述方法:

**程序 1:**

```
// Java Program Demonstrate clone()
// method of ConcurrentSkipListMap

import java.util.concurrent.ConcurrentSkipListMap;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the map
        // using ConcurrentSkipListMap()
        ConcurrentSkipListMap<Integer, Integer> mpp
            = new ConcurrentSkipListMap<Integer,
                                        Integer>();

        // Adding elements to this map
        mpp.put(1, 1);
        mpp.put(5, 2);
        mpp.put(2, 7);

        // Printing the ConcurrentSkipListMap
        System.out.println("Map: " + mpp);

        // Cloning the ConcurrentSkipListMap
        ConcurrentSkipListMap<Integer, Integer>
            clone_mpp = mpp.clone();

        // Adding elements to the clone map
        clone_mpp.put(7, 9);

        System.out.println("Cloned map is:  "
                           + clone_mpp);
    }
}
```

**输出:**

```
Map: {1=1, 2=7, 5=2}
Cloned map is:  {1=1, 2=7, 5=2, 7=9}

```

**程序二:**

```
// Java Program Demonstrate clone()
// method of ConcurrentSkipListMap

import java.util.concurrent.ConcurrentSkipListMap;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the map
        // using ConcurrentSkipListMap()
        ConcurrentSkipListMap<Integer, Integer>
            mpp = new ConcurrentSkipListMap<Integer,
                                            Integer>();

        // Adding elements to this map
        mpp.put(10, 5);
        mpp.put(54, 20);
        mpp.put(2, 7);

        // Printing the ConcurrentSkipListMap
        System.out.println("Map: " + mpp);

        // Cloning the ConcurrentSkipListMap
        ConcurrentSkipListMap<Integer, Integer>
            clone_mpp = mpp.clone();

        // Adding elements to the clone map
        clone_mpp.put(17, 9);

        System.out.println("Cloned map is:  "
                           + clone_mpp);
    }
}
```

**输出:**

```
Map: {2=7, 10=5, 54=20}
Cloned map is:  {2=7, 10=5, 17=9, 54=20}

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrentskiplistmap . html # clone–](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/ConcurrentSkipListMap.html#clone--)