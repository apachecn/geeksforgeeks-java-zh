# Java 中的 HashMap 大小()方法

> 原文:[https://www.geeksforgeeks.org/hashmap-size-method-in-java/](https://www.geeksforgeeks.org/hashmap-size-method-in-java/)

HashMap 类的 java.util.HashMap.size()方法用于获取映射的大小，该大小是指 Map 中键值对或映射的数量。

**语法:**

```
Hash_Map.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回地图的大小，这也意味着地图中存在的键值对的数量。

下面的程序说明了 java.util.HashMap.size():
程序 1:将字符串值映射到整数键。

```
// Java code to illustrate the size() method
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

        // Displaying the size of the map
        System.out.println("The size of the map is " + hash_map.size());
    }
}
```

**Output:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The size of the map is 5

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the size() method
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

        // Displaying the size of the map
        System.out.println("The size of the map is " + hash_map.size());
    }
}
```

**Output:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The size of the map is 4

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。