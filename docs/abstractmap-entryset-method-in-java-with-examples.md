# Java 中的抽象映射 entrySet()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract map-entryset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-entryset-method-in-java-with-examples/)

Java 中的 **AbstractMap.entrySet()** 方法用于创建一组包含在地图中的相同元素。它基本上返回抽象地图的集合视图，或者我们可以创建一个新的集合并将地图元素存储到其中。

**语法:**

```java
AbstractMap.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与抽象映射具有相同元素的集合。

下面的程序用来说明 java.util.AbstractMap.entrySet()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the entrySet() method

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

        // Using entrySet() to get the set view
        System.out.println("The set is: "
                           + abs_map.entrySet());
    }
}
```

**输出:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The set is: [20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4]

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the entrySet() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<String, Integer>
            abs_map = new HashMap<String, Integer>();

        // Mapping int values to string keys
        abs_map.put("Geeks", 10);
        abs_map.put("4", 15);
        abs_map.put("Geeks", 20);
        abs_map.put("Welcomes", 25);
        abs_map.put("You", 30);

        // Displaying the AbstractMap
        System.out.println("Initial Mappings are: "
                           + abs_map);

        // Using entrySet() to get the set view
        System.out.println("The set is: "
                           + abs_map.entrySet());
    }
}
```

**输出:**

```java
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The set is: [4=15, Geeks=20, You=30, Welcomes=25]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。