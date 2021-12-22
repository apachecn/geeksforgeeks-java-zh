# Java 中的 ConcurrentHashMap 元素()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-elements-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrenthashmap-elements-method-in-java-with-examples/)

Java 中 **ConcurrentHashMap 类**的**元素()**方法用于获取表中存在的值的枚举。

**语法:**

```java
Enumeration enu = ConcurrentHashMap.elements()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回哈希表值的枚举。

下面的程序用来说明 elements()方法的工作原理:

**程序 1:**

```java
// Java code to illustrate the elements() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMap_Demo {
    public static void main(String[] args)
    {

        // Creating an empty hash_map
        ConcurrentHashMap<Integer, String>
            hash_map = new ConcurrentHashMap<Integer,
                                             String>();

        // Mapping elements into the map
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Displaying the hash_map
        System.out.println("The Map is: " + hash_map);

        // Creating an empty enumeration to store
        Enumeration enu = hash_map.elements();

        System.out.println("The enumeration of values are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**Output:**

```java
The Map is: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The enumeration of values are:
Geeks
Welcomes
Geeks
You
4

```

**程序 2:**

```java
// Java code to illustrate the elements() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMap_Demo {
    public static void main(String[] args)
    {

        // Creating an empty hash_map
        ConcurrentHashMap<String, Integer>
            hash_map = new ConcurrentHashMap<String,
                                             Integer>();

        // Inserting elements into the map
        hash_map.put("Geeks", 10);
        hash_map.put("4", 15);
        hash_map.put("Geeks", 20);
        hash_map.put("Welcomes", 25);
        hash_map.put("You", 30);

        // Displaying the hash_map
        System.out.println("The Map is: " + hash_map);

        // Creating an empty enumeration to store
        Enumeration enu = hash_map.elements();

        System.out.println("The enumeration of values are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**Output:**

```java
The Map is: {4=15, Geeks=20, You=30, Welcomes=25}
The enumeration of values are:
15
20
30
25

```