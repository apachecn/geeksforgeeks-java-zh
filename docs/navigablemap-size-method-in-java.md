# Java 中的 NavigableMap size()方法

> 原文:[https://www . geesforgeks . org/naviglamblap-size-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-size-method-in-java/)

导航映射接口的 size()方法用于获取映射的大小，映射的大小是指映射中键值对或映射的数量。

**语法:**

```java
NavigableMap.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回地图的大小，这也意味着地图中存在的键值对的数量。

下面的程序说明了 size()方法的工作原理:
**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the size() method
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

        // Displaying the size of the map
        System.out.println("The size of the map is " + nav_map.size());
    }
}
```

**Output:**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The size of the map is 5

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the size() method
import java.util.*;

public class NavigableMap_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        NavigableMap<String, Integer> nav_map = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        nav_map.put("Geeks", 10);
        nav_map.put("4", 15);
        nav_map.put("Geeks", 20);
        nav_map.put("Welcomes", 25);
        nav_map.put("You", 30);

        // Displaying the NavigableMap
        System.out.println("Initial Mappings are: " + nav_map);

        // Displaying the size of the map
        System.out.println("The size of the map is " + nav_map.size());
    }
}
```

**Output:**

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The size of the map is 4

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。