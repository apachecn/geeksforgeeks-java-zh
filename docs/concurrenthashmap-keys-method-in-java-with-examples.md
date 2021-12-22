# Java 中的 ConcurrentHashMap keys()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-keys-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrenthashmap-keys-method-in-java-with-examples/)

Java 中 **ConcurrentHashMap 类**的**key()**方法用于获取 HashMap 中存在的键的枚举。

**语法:**

```java
Enumeration enu = ConcurrentHashMap.keys()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回 ConcurrentHashMap 的键的枚举。

下面的程序用来说明 key()方法的工作原理:

**程序 1:**

```java
// Java code to illustrate the keys() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty ConcurrentHashMap
        ConcurrentHashMap<Integer, String>
            hash_map = new ConcurrentHashMap<Integer,
                                             String>();

        // Inserting elements into the map
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Displaying the ConcurrentHashMap
        System.out.println("The Map is: " + hash_map);

        // Creating an empty enumeration to store
        Enumeration enu = hash_map.keys();

        System.out.println("The enumeration of keys are:");

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
The enumeration of keys are:
20
25
10
30
15

```

**程序 2:**

```java
// Java code to illustrate the keys() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty ConcurrentHashMap
        ConcurrentHashMap<String, Integer>
            hash_map = new ConcurrentHashMap<String,
                                             Integer>();

        // Inserting elements into the table
        hash_map.put("Geeks", 10);
        hash_map.put("4", 15);
        hash_map.put("Geeks", 20);
        hash_map.put("Welcomes", 25);
        hash_map.put("You", 30);

        // Displaying the ConcurrentHashMap
        System.out.println("The Map is: " + hash_map);

        // Creating an empty enumeration to store
        Enumeration enu = hash_map.keys();

        System.out.println("The enumeration of keys are:");

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
The enumeration of keys are:
4
Geeks
You
Welcomes

```