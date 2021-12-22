# Java 中的 NavigableMap clear()方法

> 原文:[https://www . geesforgeks . org/naviglamblemap-clear-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-clear-method-in-java/)

Java 中 NavigableMap 接口的 clear()方法用于清除和移除指定 Map 中的所有元素或映射。

**语法:**

```
NavigableMap.clear()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

以下程序用于说明 clear()方法的工作原理:
**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the clear() method
import java.util.*;

public class NavigableMap_Demo {
    public static void main(String[] args)
    {

        // Creating an empty NavigableMap
        NavigableMap<Integer, String> nav_map = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        nav_map.put(10, "Geeks");
        nav_map.put(15, "4");
        nav_map.put(20, "Geeks");
        nav_map.put(25, "Welcomes");
        nav_map.put(30, "You");

        // Displaying the NavigableMap
        System.out.println("Initial Mappings are: " + nav_map);

        // Clearing the tree map using clear()
        nav_map.clear();

        // Displaying the final NavigableMap
        System.out.println("Finally the map looks like: " + nav_map);
    }
}
```

**Output:**

```
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Finally the map looks like: {}

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the clear() method
import java.util.*;

public class NavigableMap_Demo {
    public static void main(String[] args)
    {

        // Creating an empty NavigableMap
        TreeMap<String, Integer> nav_map = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        nav_map.put("Geeks", 10);
        nav_map.put("4", 15);
        nav_map.put("Geeks", 20);
        nav_map.put("Welcomes", 25);
        nav_map.put("You", 30);

        // Displaying the NavigableMap
        System.out.println("Initial Mappings are: " + nav_map);

        // Clearing the tree map using clear()
        nav_map.clear();

        // Displaying the final NavigableMap
        System.out.println("Finally the map looks like: " + nav_map);
    }
}
```

**Output:**

```
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
Finally the map looks like: {}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。