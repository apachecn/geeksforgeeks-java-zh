# 抽象映射包含 Java 中的 Key()方法，示例

> 原文:[https://www . geesforgeks . org/abstract map-contains key-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-containskey-method-in-java-with-examples/)

**抽象映射. containsKey()** 方法用于检查特定的键是否被映射到抽象映射中。它将关键元素作为参数，如果该元素在映射中被映射，则返回 True。

**语法:**

```java
AbstractMap.containsKey(*key_element*)
```

**参数:**该方法只取一个参数 *key_element* ，该参数是指映射应该在地图内部检查的键。

**返回值:**如果检测到键的存在，则该方法返回布尔值 true，否则返回 false。

下面的程序用来说明 AbstractMap.containsKey()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the containsKey() method

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

        // Checking for the key_element '20'
        System.out.println("Is the key '20' present? "
                           + abs_map.containsKey(20));

        // Checking for the key_element '5'
        System.out.println("Is the key '5' present? "
                           + abs_map.containsKey(5));
    }
}
```

**输出:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Is the key '20' present? true
Is the key '5' present? false

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the containsKey() method

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

        // Checking for the key_element 'Welcomes'
        System.out.println("Is the key"
                           + " 'Welcomes' present? "
                           + abs_map.containsKey("Welcomes"));

        // Checking for the key_element 'World'
        System.out.println("Is the key"
                           + " 'World' present? "
                           + abs_map.containsKey("World"));
    }
}
```

**输出:**

```java
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
Is the key 'Welcomes' present? true
Is the key 'World' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。