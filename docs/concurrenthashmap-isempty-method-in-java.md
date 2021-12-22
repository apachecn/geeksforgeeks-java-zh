# Java 中的 ConcurrentHashMap isEmpty()方法

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-isempty-method-in-Java/](https://www.geeksforgeeks.org/concurrenthashmap-isempty-method-in-java/)

java . util . concurrenthashmap 的 **isEmpty()** 方法是 Java 中的一个内置函数，它检查*这个*映射是否包含任何键值映射，并返回一个布尔值。

**语法:**

```
public boolean isEmpty()
```

**返回值:**该函数返回一个**布尔值**。如果 ConcurrentHashMap 为空，则返回 true，否则返回 false。

以下程序说明了 **isEmpty()** 方法的使用:

**程序 1:** 在这个程序中，ConcurrentHashMap 是非空的。

```
// Java Program Demonstrate isEmpty()
// method of ConcurrentHashMap */

import java.util.concurrent.*;

class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {

        ConcurrentHashMap<Integer, String>
            chm = new ConcurrentHashMap<Integer, String>();

        chm.put(100, "Geeks");
        chm.put(101, "for");
        chm.put(102, "Geeks");

        // Checking for the emptiness of Map
        if (chm.isEmpty()) {
            System.out.println("The ConcurrentHashMap"
                               + " is empty.");
        }
        else {
            // Displaying the ConcurrentHashMap
            System.out.println("The Mappings are: "
                               + chm);
        }
    }
}
```

**Output:**

```
The Mappings are: {100=Geeks, 101=for, 102=Geeks}

```

**程序 2:** 在这个程序中，ConcurrentHashMap 是非空的。

```
// Java Program Demonstrate isEmpty()
// method of ConcurrentHashMap */

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        ConcurrentHashMap chm = new ConcurrentHashMap();

        // Checking for the emptiness of Map
        if (chm.isEmpty()) {
            System.out.println("The ConcurrentHashMap"
                               + " is empty.");
        }
        else {
            // Displaying the ConcurrentHashMap
            System.out.println("The Mappings are: "
                               + chm);
        }
    }
}
```

**Output:**

```
The ConcurrentHashMap is empty.

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrenthashmap . html # isEmpty()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html#isEmpty())