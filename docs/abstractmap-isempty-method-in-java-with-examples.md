# Java 中的抽象映射 isEmpty()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract map-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-isempty-method-in-java-with-examples/)

AbstractMap 类的 **AbstractMap.isEmpty()** 方法用于检查地图的空性。如果映射中没有键值对或映射，则该方法返回真，否则返回假。

**语法:**

```java
AbstractMap.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**如果映射为空或者不包含任何映射对，则该方法返回布尔值 true，否则返回布尔值 false。

下面的程序说明了 AbstractMap.isEmpty()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the isEmpty() method

import java.util.*;

public class AbstractMap_Demo {
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
        System.out.println("The Mappings are: "
                           + abs_map);

        // Checking for the emptiness of Map
        System.out.println("Is the map empty? "
                           + abs_map.isEmpty());
    }
}
```

**输出:**

```java
The Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
Is the map empty? false

```

**程序 2:** 为空哈希表

```java
// Java code to illustrate the isEmpty() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<String, Integer>
            abs_map = new HashMap<String, Integer>();

        // Displaying the AbstractMap
        System.out.println("The Mappings are: "
                           + abs_map);

        // Checking for the emptiness of Map
        System.out.println("Is the map empty? "
                           + abs_map.isEmpty());
    }
}
```

**输出:**

```java
The Mappings are: {}
Is the map empty? true

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。