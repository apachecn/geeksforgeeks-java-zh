# Java 中的 HashMap entrySet()方法

> 原文:[https://www . geesforgeks . org/hashmap-entryset-method-in-Java/](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/)

java 中的 java.util.HashMap.entrySet()方法用于创建一组包含在哈希映射中的相同元素。它基本上返回哈希映射的集合视图，或者我们可以创建一个新的集合并将映射元素存储到其中。

**语法:**

```
hash_map.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与哈希映射具有相同元素的集合。

下面的程序用来说明 java.util.HashMap.entrySet()方法:
**程序 1:** 将字符串值映射为整数键。

```
// Java code to illustrate the entrySet() method
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

        // Using entrySet() to get the set view
        System.out.println("The set is: " + hash_map.entrySet());
    }
}
```

**Output:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The set is: [20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4]

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the entrySet() method
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

        // Using entrySet() to get the set view
        System.out.println("The set is: " + hash_map.entrySet());
    }
}
```

**Output:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The set is: [4=15, Geeks=20, You=30, Welcomes=25]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。