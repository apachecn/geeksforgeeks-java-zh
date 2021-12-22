# Java 中的 ConcurrentHashMap entrySet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-entryset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrenthashmap-entryset-method-in-java-with-examples/)

Java 中 **ConcurrentHashMap** 的 **entrySet()** 方法用于从并发哈希映射中包含的相同元素创建一个集合。它基本上返回并发哈希映射的集合视图，或者我们可以创建一个新的集合并将映射元素存储到其中。

**语法:**

```
ConcurrentHashMap.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与并发哈希映射具有相同元素的集合。

以下程序用于说明 entrySet()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the entrySet() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty ConcurrentHashMap
        ConcurrentHashMap<Integer, String>
            hash_map = new ConcurrentHashMap<Integer, String>();

        // Mapping string values to int keys
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Displaying the HashMap
        System.out.println("Initial Mappings are: " + hash_map);

        // Using entrySet() to get the set view
        System.out.println("The set is: " + hash_map.entrySet());
    }
}
```

**输出:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The set is: [20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4]

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the entrySet() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty ConcurrentHashMap
        ConcurrentHashMap<String, Integer>
            hash_map = new ConcurrentHashMap<String, Integer>();

        // Mapping int values to string keys
        hash_map.put("Geeks", 10);
        hash_map.put("4", 15);
        hash_map.put("Geeks", 20);
        hash_map.put("Welcomes", 25);
        hash_map.put("You", 30);

        // Displaying the HashMap
        System.out.println("Initial Mappings are: " + hash_map);

        // Using entrySet() to get the set viewa
        System.out.println("The set is: " + hash_map.entrySet());
    }
}
```

**输出:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The set is: [4=15, Geeks=20, You=30, Welcomes=25]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。