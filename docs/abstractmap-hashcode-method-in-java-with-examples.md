# Java 中的抽象映射 hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract map-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-hashcode-method-in-java-with-examples/)

Java 中的 **AbstractMap.hashCode()** 方法用于获取特定这个 AbstractMap 的哈希代码值。映射由多个存储键值对的桶组成。每个存储桶都有一个唯一的标识，当一个键值对被插入到存储桶中时，该键的 hashcode 与存储桶的标识符相匹配，如果匹配，则该对被成功存储。这就是哈希代码的工作原理。

**语法:**

```
AbstractMap.hashCode()
```

**参数:**该方法不接受任何参数。

**返回值:**方法返回地图的 hashcode 值。

下面的程序用来说明 AbstractMap.hashCode()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the hashCode() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<Integer, String>
            abs_map = new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        abs_map.put(10, "Geeks");
        abs_map.put(15, "4");
        abs_map.put(20, "Geeks");
        abs_map.put(25, "Welcomes");
        abs_map.put(30, "You");

        // Displaying the AbstractMap
        System.out.println("Initial Mappings are: "
                           + abs_map);

        // Getting the hashcode value for the map
        System.out.println("The hashcode value of the map: "
                           + abs_map.hashCode());
    }
}
```

**输出:**

```
Initial Mappings are: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
The hashcode value of the map: 2043437408

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the hashCode() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<String, Integer>
            abs_hash = new IdentityHashMap<String, Integer>();

        // Mapping int values to string keys
        abs_hash.put("Geeks", 10);
        abs_hash.put("4", 15);
        abs_hash.put("Geeks", 20);
        abs_hash.put("Welcomes", 25);
        abs_hash.put("You", 30);

        // Displaying the AbstractMap
        System.out.println("Initial Mappings are: "
                           + abs_hash);

        // Getting the hashcode value for the map
        System.out.println("The hashcode value of the map: "
                           + abs_hash.hashCode());
    }
}
```

**输出:**

```
Initial Mappings are: {Geeks=20, Welcomes=25, You=30, 4=15}
The hashcode value of the map: 751311572

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。