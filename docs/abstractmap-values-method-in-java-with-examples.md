# Java 中的抽象映射值()方法，示例

> 原文:[https://www . geesforgeks . org/abstract map-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-values-method-in-java-with-examples/)

Java 中抽象映射类的 **AbstractMap.values()** 方法用于从映射的值中创建一个集合。它基本上返回抽象映射中值的集合视图。

**语法:**

```java
AbstractMap.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法用于返回包含地图所有值的集合视图。

下面的程序用来说明 AbstractMap.values()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the values() method

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

        // Using values() to get the set view of values
        System.out.println("The collection is: "
                           + abs_map.values());
    }
}
```

**输出:**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The collection is: [Geeks, 4, Geeks, Welcomes, You]

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the values() method

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

        // Using values() to get the set view of values
        System.out.println("The collection is: "
                           + abs_map.values());
    }
}
```

**输出:**

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The collection is: [15, 20, 25, 30]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。