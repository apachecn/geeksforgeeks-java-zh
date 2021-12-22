# Java 中的 HashMap remove()方法

> 原文:[https://www . geesforgeks . org/hashmap-remove-method-in-Java/](https://www.geeksforgeeks.org/hashmap-remove-method-in-java/)

java.util.HashMap.remove()是 HashMap 类的内置方法，用于从映射中移除任何特定键的映射。它基本上删除了地图中任何特定键的值。
**语法:**

```
Hash_Map.remove(*Object key*)
```

**参数:**该方法采用一个参数*键*，其映射将从地图中移除。
**返回值:**该方法返回之前映射到指定键的值，如果该键存在，则该方法返回空值。
下面的程序说明了 java.util.HashMap.remove()方法的工作:
**程序 1:** 当传递一个现有的密钥时。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the remove() method
import java.util.*;

public class Hash_Map_Demo {
public static void main(String[] args) {

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

    // Removing the existing key mapping
    String returned_value = (String)hash_map.remove(20);

    // Verifying the returned value
    System.out.println("Returned value is: "+ returned_value);

    // Displaying the new map
    System.out.println("New map is: "+ hash_map);
}
}
```

**Output:** 

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Returned value is: Geeks
New map is: {25=Welcomes, 10=Geeks, 30=You, 15=4}
```

**程序 2:** 传递新密钥时。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the remove() method
import java.util.*;

public class Hash_Map_Demo {
   public static void main(String[] args) {

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

      // Removing the new key mapping
      String returned_value = (String)hash_map.remove(50);

      // Verifying the returned value
      System.out.println("Returned value is: "+ returned_value);

      // Displaying the new map
      System.out.println("New map is: "+ hash_map);
   }
}
```

**Output:** 

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Returned value is: null
New map is: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。