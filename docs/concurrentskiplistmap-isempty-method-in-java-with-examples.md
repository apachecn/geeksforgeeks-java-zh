# Java 中的 ConcurrentSkipListMap isEmpty()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-isempty-method-in-java-with-examples/)

**java . util . concurrentskiplistmap**的 **isEmpty()** 方法是 Java 中的内置函数，它返回布尔值，即如果该映射不包含键值映射，则返回 true，否则返回 false。

**语法:**

```
public boolean isEmpty()

```

**参数:**函数不接受任何参数。

**返回值:**如果该映射不包含键值映射，则函数返回真，否则返回假。

下面的程序说明了上述方法:

**程序 1:**

```
// Java Program Demonstrate isEmpty()
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

        // checking if map is empty
        System.out.println(mpp.isEmpty());
    }
}
```

**输出:**

```
false

```

**程序二:**

```
// Java Program Demonstrate isEmpty()
// method of ConcurrentSkipListMap

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the map
        ConcurrentSkipListMap<Integer, Integer>
            mpp = new ConcurrentSkipListMap<Integer,
                                            Integer>();

        // checking if map is empty
        System.out.println(mpp.isEmpty());
    }
}
```

**输出:**

```
true

```

**参考:**[https://docs . Oracle . com/javae/8/docs/API/Java/util/concurrent/concurrents kiplistmap . html # isempty】](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListMap.html#isEmpty--)