# Java 中的 ConcurrentHashMap keySet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-key set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrenthashmap-keyset-method-in-java-with-examples/)

Java 中**concurrenthashmap 类**的 **keySet()** 方法用于创建哈希映射中包含的一组关键元素。它基本上返回一个键的集合视图，或者我们可以创建一个新的集合并将键元素存储在其中。

**语法:**

```
ConcurrentHashMap.keySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个具有哈希映射键的集合。

下面的程序用来说明键集()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the keys() method

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
        System.out.println("The set is: "
                           + hash_map.keySet());
    }
}
```

**输出:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The set is: [20, 25, 10, 30, 15]

```

**程序 2:** 将整数值映射到字符串键。

```
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

        // Displaying the HashMap
        System.out.println("Initial Mappings are: "
                           + hash_map);

        // Using keySet() to get the set view of keys
        System.out.println("The set is: "
                           + hash_map.keySet());
    }
}
```

**输出:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The set is: [4, Geeks, You, Welcomes]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。