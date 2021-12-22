# Java 中的抽象映射 putAll()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract map-putall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-putall-method-in-java-with-examples/)

**抽象映射. putAll()** 是抽象映射类的一个内置方法，用于复制操作。该方法将所有元素(即映射)从一个映射复制到另一个映射。

**语法:**

```java
new_abstract_map.putAll(*exist_abstract_map*)
```

**参数:**该方法取一个参数 *exist_abstract_map* ，指的是我们要复制的现有地图。

**返回值:**该方法不返回值。

**异常:**如果我们要复制的地图为空，该方法抛出*空指针异常*。

下面的程序说明了 AbstractMap.putAll()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the putAll() method

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

        // Creating a new abstract map and copying
        AbstractMap<Integer, String>
            new_abs_map = new HashMap<Integer, String>();

        new_abs_map.putAll(abs_map);

        // Displaying the final AbstractMap
        System.out.println("The new map looks like this: "
                           + new_abs_map);
    }
}
```

**输出:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The new map looks like this: {25=Welcomes, 10=Geeks, 20=Geeks, 30=You, 15=4}

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the putAll() method

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

        // Creating a new hash map and copying
        AbstractMap<String, Integer>
            new_abs_map = new HashMap<String, Integer>();

        new_abs_map.putAll(abs_map);

        // Displaying the final AbstractMap
        System.out.println("The new map looks like this: "
                           + new_abs_map);
    }
}
```

**输出:**

```java
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The new map looks like this: {Geeks=20, 4=15, You=30, Welcomes=25}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。