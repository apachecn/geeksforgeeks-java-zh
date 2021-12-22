# 抽象地图放()方法在 Java 中用例子

> 原文:[https://www . geesforgeks . org/abstract map-put-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-put-method-in-java-with-examples/)

AbstractMap 的 **AbstractMap.put()** 方法用于将映射插入到地图中。这意味着我们可以将特定的键及其映射到的值插入到特定的映射中。如果传递了现有的键，则以前的值将被新值替换。如果传递了一个新的对，那么该对将作为一个整体被插入。

**语法:**

```java
AbstractMap.put(*key, value*)
```

**参数:**该方法取两个参数，都是 AbstractMap 的 Object 类型:

*   *Key:* This refers to the key element that needs to be inserted into the Map for mapping.
*   *Value:* This refers to the value to which the above key is mapped.

**返回值:**如果传递了一个现有的键，则返回前一个值。如果传递了新的对，则返回空值。

下面的程序用来说明 AbstractMap.put()方法的工作原理:

**程序 1:** 传递现有密钥时。

```java
// Java code to illustrate the put() method

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

        // Inserting existing key along with new value
        String
            returned_value
            = (String)abs_map.put(20, "All");

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
New map is: {20=All, 25=Welcomes, 10=Geeks, 30=You, 15=4}

```

**程序 2:** 传递新钥匙时。

```java
// Java code to illustrate the put() method

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

        // Inserting existing key along with new value
        String
            returned_value
            = (String)abs_map.put(50, "All");

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
New map is: {50=All, 20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。