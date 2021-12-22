# Java 中的 ConcurrentHashMap values()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrenthashmap-values-method-in-java-with-examples/)

Java 中 **ConcurrentHashMap 类**的**值()**方法用于从地图的值中创建一个集合。它基本上返回 ConcurrentHashMap 中值的集合视图。

**语法:**

```java
ConcurrentHashMap.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法用于返回包含地图所有值的集合视图。

以下程序用于说明 ConcurrentHashMap.values()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the values() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty ConcurrentHashMap
        ConcurrentHashMap<Integer, String> hash_map
            = new ConcurrentHashMap<Integer, String>();

        // Mapping string values to int keys
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Displaying the HashMap
        System.out.println("Initial Mappings are: "
                           + hash_map);

        // Using keySet() to get the set view of keys
        System.out.println("The Collection is: "
                           + hash_map.values());
    }
}
```

**输出:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The Collection is: [Geeks, Welcomes, Geeks, You, 4]

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the values() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty ConcurrentHashMap
        ConcurrentHashMap<String, Integer>
            hash_map = new ConcurrentHashMap<String,
                                             Integer>();

        // Mapping int values to string keys
        hash_map.put("Geeks", 10);
        hash_map.put("4", 15);
        hash_map.put("Geeks", 20);
        hash_map.put("Welcomes", 25);
        hash_map.put("You", 30);

        // Displaying the HashMap
        System.out.println("Initial Mappings are: "
                           + hash_map);

        // Using keySet() to get the set view of keys
        System.out.println("The Collection is: "
                           + hash_map.values());
    }
}
```

**输出:**

```java
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The Collection is: [15, 20, 30, 25]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。