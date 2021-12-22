# Java 中 LinkedHashMap clear()方法

> 原文:[https://www . geeksforgeeks . org/link edhashmap-clear-method-in-Java/](https://www.geeksforgeeks.org/linkedhashmap-clear-method-in-java/)

java.util.LinkedHashMap.clear()是 java 中 LinkedHashMap 类的一个内置方法，用于清除所表示的 LinkedHashMap 中的所有元素或映射。执行操作后，地图将变为空白。

**语法:**

```java
Linked_Hash_Map.clear()
```

**参数:**该方法不取任何参数。

**返回值:**该方法不返回值。

下面的程序说明了 java.util.LinkedHashMap.clear()方法:
**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the clear() method
import java.util.*;

public class Linked_Hash_Map_Demo {
    public static void main(String[] args)
    {
        // Creating an empty LinkedHashMap
        LinkedHashMap<Integer, String> li_hash_map =
        new LinkedHashMap<Integer, String>();

        // Mapping string values to int keys
        li_hash_map.put(10, "Geeks");
        li_hash_map.put(15, "4");
        li_hash_map.put(20, "Geeks");
        li_hash_map.put(25, "Welcomes");
        li_hash_map.put(30, "You");

        // Displaying the LinkedHashMap
        System.out.println("Initial Mappings are: " + li_hash_map);

        // Clearing the linked hash map using clear()
        li_hash_map.clear();

        // Displaying the final HashMap
        System.out.println("Finally the maps look like this: " + li_hash_map);
    }
}
```

**Output:**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Finally the maps look like this: {}

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the clear() method
import java.util.*;

public class Linked_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty LinkedHashMap
        LinkedHashMap<String, Integer> li_hash_map =
        new LinkedHashMap<String, Integer>();

        // Mapping int values to string keys
        li_hash_map.put("Geeks", 10);
        li_hash_map.put("4", 15);
        li_hash_map.put("Geeks", 20);
        li_hash_map.put("Welcomes", 25);
        li_hash_map.put("You", 30);

        // Displaying the LinkedHashMap
        System.out.println("Initial Mappings are: " + li_hash_map);

        // Clearing the linked hash map using clear()
        li_hash_map.clear();

        // Displaying the final HashMap
        System.out.println("Finally the maps look like this: " + li_hash_map);
    }
}
```

**Output:**

```java
Initial Mappings are: {Geeks=20, 4=15, Welcomes=25, You=30}
Finally the maps look like this: {}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。