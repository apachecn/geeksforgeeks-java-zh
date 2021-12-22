# Java 中的 HashMap 值()方法

> 原文:[https://www . geesforgeks . org/hashmap-values-method-in-Java/](https://www.geeksforgeeks.org/hashmap-values-method-in-java/)

java 中 HashMap 类的 java.util.HashMap.values()方法用于从映射的值中创建一个集合。它基本上返回哈希表中值的集合视图。

**语法:**

```
Hash_Map.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法用于返回包含地图所有值的集合视图。

下面的程序用来说明 java.util.HashMap.values()的工作方式方法:
**程序 1:** 将字符串值映射为整数键。

```
// Java code to illustrate the values() method
import java.util.*;

public class Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty HashMap
        HashMap<Integer, String> hash_map = new HashMap<Integer, String>();

        // Mapping string values to int keys
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Displaying the HashMap
        System.out.println("Initial Mappings are: " + hash_map);

        // Using values() to get the set view of values
        System.out.println("The collection is: " + hash_map.values());
    }
}
```

**Output:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The collection is: [Geeks, Welcomes, Geeks, You, 4]

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the values() method
import java.util.*;

public class Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty HashMap
        HashMap<String, Integer> hash_map = new HashMap<String, Integer>();

        // Mapping int values to string keys
        hash_map.put("Geeks", 10);
        hash_map.put("4", 15);
        hash_map.put("Geeks", 20);
        hash_map.put("Welcomes", 25);
        hash_map.put("You", 30);

        // Displaying the HashMap
        System.out.println("Initial Mappings are: " + hash_map);

        // Using values() to get the set view of values
        System.out.println("The collection is: " + hash_map.values());
    }
}
```

**Output:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The collection is: [15, 20, 30, 25]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。