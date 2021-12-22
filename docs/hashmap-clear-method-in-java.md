# Java 中的 HashMap clear()方法

> 原文:[https://www.geeksforgeeks.org/hashmap-clear-method-in-java/](https://www.geeksforgeeks.org/hashmap-clear-method-in-java/)

java 中的 java.util.HashMap.clear()方法用于清除和移除指定 HashMap 中的所有元素或映射。

**语法:**

```
Hash_Map.clear()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

下面的程序用来说明 java.util.HashMap.clear()方法的工作原理:
**程序 1:** 将字符串值映射为整数键。

```
// Java code to illustrate the clear() method
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

        // Clearing the hash map using clear()
        hash_map.clear();

        // Displaying the final HashMap
        System.out.println("Finally the maps look like this: " + hash_map);
    }
}
```

**Output:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Finally the maps look like this: {}

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the clear() method
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

        // Clearing the hash map using clear()
        hash_map.clear();

        // Displaying the final HashMap
        System.out.println("Finally the maps look like this: " + hash_map);
    }
}
```

**Output:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
Finally the maps look like this: {}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。