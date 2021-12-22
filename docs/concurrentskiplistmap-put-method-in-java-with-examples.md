# Java 中的 ConcurrentSkipListMap put()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistmap-put-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistmap-put-method-in-java-with-examples/)

**[java . util . concurrentskiplistmap](https://www.geeksforgeeks.org/concurrentskiplistset-in-java-with-examples/)**的 **put()** 方法是 Java 中的内置函数，它将指定的值与该映射中的指定键相关联。如果映射先前包含键的映射，则替换旧值。

**语法:**

```java
public V put(K key, V value)

```

**参数:**该函数接受两个强制参数:

*   **key** specifies the key associated with the specified value.
*   **Value:** Specifies the value associated with the specified key.

**返回值:**该函数返回与指定键关联的前一个值。如果指定的键没有映射，则此方法返回 null。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java Program Demonstrate put()
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

        // put() operation on the map
        System.out.println("After put(): "
                           + mpp);
    }
}
```

**输出:**

```java
After put(): {1=1, 2=2, 3=3, 4=4, 5=5}

```

**程序二:**

```java
// Java Program Demonstrate put()
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
        for (int i = 1; i <= 9; i++)
            mpp.put(i, i);

        // put() operation on the map
        System.out.println("After put(): "
                           + mpp);
    }
}
```

**输出:**

```java
After put(): {1=1, 2=2, 3=3, 4=4, 5=5, 6=6, 7=7, 8=8, 9=9}

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrentskiplistmap . html # put-K-V-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/ConcurrentSkipListMap.html#put-K-V-)