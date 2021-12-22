# 用示例在 Java 中抽象映射 clear()方法

> 原文:[https://www . geesforgeks . org/abstract map-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-clear-method-in-java-with-examples/)

Java 中的 **AbstractMap.clear()** 方法用于清除和移除指定地图中的所有元素或映射。

**语法:**

```java
AbstractMap.clear()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

下面的程序用来说明 AbstractMap.clear()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the clear() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
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

        // Clearing the map using clear()
        abs_map.clear();

        // Displaying the final AbstractMap
        System.out.println("Finally the map looks like: "
                           + abs_map);
    }
}
```

**输出:**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Finally the map looks like: {}

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the clear() method

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

        // Clearing the abstract map using clear()
        abs_map.clear();

        // Displaying the final AbstractMap
        System.out.println("Finally the map looks like: "
                           + abs_map);
    }
}
```

**输出:**

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
Finally the map looks like: {}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。