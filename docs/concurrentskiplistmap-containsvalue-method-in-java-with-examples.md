# 在 Java 中 ConcurrentSkipListMap contains value()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-contains value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-containsvalue-method-in-java-with-examples/)

**java . util . concurrentskiplistmap**的 **containsValue()** 方法是 Java 中的内置函数，如果此映射将一个或多个键映射到指定值，则返回 **true** 。如果没有要映射的键，该方法将返回 null。当指定的值为空时，该方法引发 NullPointerException。
**语法:**

```
public boolean containsValue(Object ob)
```

**参数:**该函数接受单个强制参数 **ob** ，该参数指定要测试其存在的值。
**返回值:**如果存在映射，函数返回真，否则返回假。
**异常:**当指定值为空时，该方法抛出 NullPointerException。
以下程序举例说明上述方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate containsValue()
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

        // checking whether object present in map
        System.out.println(mpp.containsValue(4));
    }
}
```

**Output:** 

```
true
```

**节目:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate containsValue()
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

        // checking whether object present in map
        System.out.println(mpp.containsValue(7));
    }
}
```

**Output:** 

```
false
```

**参考:**T2【https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistmap . html # contains value-Java . lang . object-T4】