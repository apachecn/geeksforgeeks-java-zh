# Java 中的抽象映射大小()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract map-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-size-method-in-java-with-examples/)

AbstractMap 类的 **AbstractMap.size()** 方法用于获取映射的大小，该大小是指映射中键值对或映射的数量。

**语法:**

```java
AbstractMap.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回地图的**大小**，这也意味着地图中存在的键值对的数量。

下面的程序说明了 AbstractMap.size()的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the size() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<Integer, String>
            abs_map = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        abs_map.put(10, "Geeks");
        abs_map.put(15, "4");
        abs_map.put(20, "Geeks");
        abs_map.put(25, "Welcomes");
        abs_map.put(30, "You");

        // Displaying the AbstractMap
        System.out.println("Initial Mappings are: "
                           + abs_map);

        // Displaying the size of the map
        System.out.println("The size of the map is "
                           + abs_map.size());
    }
}
```

**输出:**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The size of the map is 5

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the size() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<String, Integer>
            abs_map = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        abs_map.put("Geeks", 10);
        abs_map.put("4", 15);
        abs_map.put("Geeks", 20);
        abs_map.put("Welcomes", 25);
        abs_map.put("You", 30);

        // Displaying the AbstractMap
        System.out.println("Initial Mappings are: "
                           + abs_map);

        // Displaying the size of the map
        System.out.println("The size of the map is "
                           + abs_map.size());
    }
}
```

**输出:**

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The size of the map is 4

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。