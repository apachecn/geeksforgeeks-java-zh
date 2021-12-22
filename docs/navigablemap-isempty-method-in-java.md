# Java 中的 NavigableMap isEmpty()方法

> 原文:[https://www . geesforgeks . org/naviglambmap-isempty-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-isempty-method-in-java/)

NavigableMap 接口的 isEmpty()方法用于检查地图的空白。如果映射中没有键值对或映射，则该方法返回真，否则返回假。

**语法:**

```
NavigableMap.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**如果映射为空或者不包含任何映射对，则该方法返回布尔值 true，否则返回布尔值 false。

下面的程序说明了 isEmpty()方法的工作原理:
**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the isEmpty() method
import java.util.*;

public class NavigableMap_Demo {
    public static void main(String[] args)
    {

        // Creating an empty NavigableMap
        NavigableMap<String, Integer> nav_map = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        nav_map.put("Geeks", 10);
        nav_map.put("4", 15);
        nav_map.put("Geeks", 20);
        nav_map.put("Welcomes", 25);
        nav_map.put("You", 30);

        // Displaying the NavigableMap
        System.out.println("The Mappings are: " + nav_map);

        // Checking for the emptiness of Map
        System.out.println("Is the map empty? " + nav_map.isEmpty());
    }
}
```

**Output:**

```
The Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
Is the map empty? false

```

**程序 2:** 为空标识哈希映射

```
// Java code to illustrate the isEmpty() method
import java.util.*;

public class NavigableMap_Demo {
    public static void main(String[] args)
    {

        // Creating an empty NavigableMap
        NavigableMap<String, Integer> nav_map = new TreeMap<String, Integer>();

        // Displaying the NavigableMap
        System.out.println("The Mappings are: " + nav_map);

        // Checking for the emptiness of Map
        System.out.println("Is the map empty? " + nav_map.isEmpty());
    }
}
```

**Output:**

```
The Mappings are: {}
Is the map empty? true

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

[Java.util.IdentityHashMap 类](https://www.geeksforgeeks.org/java-util-IdentityHashMap-class-java/)的所有方法