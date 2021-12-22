# 抽象映射移除()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/abstract map-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-remove-method-in-java-with-examples/)

**抽象映射. remove()** 是抽象映射类的内置方法，用于从映射中移除任何特定键的映射。它基本上删除了地图中任何特定键的值。

**语法:**

```java
AbstractMap.remove(*Object key*)
```

**参数:**该方法采用一个参数*键*，其映射将从地图中移除。

**返回值:**该方法返回之前映射到指定键的值，如果该键存在，则该方法返回空值。

下面的程序说明了 AbstractMap.remove()方法的工作原理:

**程序 1:** 传递现有密钥时。

```java
// Java code to illustrate the remove() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<Integer, String>
            abs_map = new HashMap<Integer, String>();

        // Mapping string values to int keys
        abs_map.put(10, "Geeks");
        abs_map.put(15, "4");
        abs_map.put(20, "Geeks");
        abs_map.put(25, "Welcomes");
        abs_map.put(30, "You");

        // Displaying the AbstractMap
        System.out.println("Initial Mappings are: "
                           + abs_map);

        // Removing the existing key mapping
        String
            returned_value
            = (String)abs_map.remove(20);

        // Verifying the returned value
        System.out.println("Returned value is: "
                           + returned_value);

        // Displayin the new map
        System.out.println("New map is: "
                           + abs_map);
    }
}
```

**输出:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Returned value is: Geeks
New map is: {25=Welcomes, 10=Geeks, 30=You, 15=4}

```

**程序 2:** 传递新钥匙时。

```java
// Java code to illustrate the remove() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<Integer, String>
            abs_map = new HashMap<Integer, String>();

        // Mapping string values to int keys
        abs_map.put(10, "Geeks");
        abs_map.put(15, "4");
        abs_map.put(20, "Geeks");
        abs_map.put(25, "Welcomes");
        abs_map.put(30, "You");

        // Displaying the AbstractMap
        System.out.println("Initial Mappings are: "
                           + abs_map);

        // Removing the new key mapping
        String
            returned_value
            = (String)abs_map.remove(50);

        // Verifying the returned value
        System.out.println("Returned value is: "
                           + returned_value);

        // Displayin the new map
        System.out.println("New map is: " + abs_map);
    }
}
```

**输出:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Returned value is: null
New map is: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。