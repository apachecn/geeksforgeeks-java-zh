# 用示例链接 Java 中的 HashMap get()方法

> 原文:[https://www . geeksforgeeks . org/linked hashmap-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedhashmap-get-method-in-java-with-examples/)

在 Java 中， [LinkedHashMap 类](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)的 *get()方法*用于检索或获取参数中提到的特定键映射的值。当映射不包含键的这种映射时，它返回空值。

```
--> java.util Package
    --> LinkedHashMap Class
         --> get() Method  
```

**语法:**

```
Linked_Hash_Map.get(*Object key_element*)
```

**参数:**一个对象类型的参数 *key_element* ，指的是应该取关联值的键。

**返回类型:**参数中与*关键元素*关联的值。

**示例 1:** 将字符串值映射到整数键。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate get() method
// of LinkedHashMap
// Mapping String Values to Integer Keys

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty HashMap
        LinkedHashMap<Integer, String> li_hash_map
            = new LinkedHashMap<Integer, String>();

        // Mapping string values to int keys
        // using put() method
        li_hash_map.put(10, "Geeks");
        li_hash_map.put(15, "4");
        li_hash_map.put(20, "Geeks");
        li_hash_map.put(25, "Welcomes");
        li_hash_map.put(30, "You");

        // Printing all elements of LinkedHashMap
        System.out.println("Initial Mappings are: "
                           + li_hash_map);

        // Getting the value of 25
        System.out.println("The Value is: "
                           + li_hash_map.get(25));

        // Getting the value of 10
        System.out.println("The Value is: "
                           + li_hash_map.get(10));
    }
}
```

**Output:** 

```
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The Value is: Welcomes
The Value is: Geeks
```

**示例 2:** 将整数值映射到字符串键

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate get() method
// Mapping Integer Values to String Keys

// Importing required classes
import java.util.*;

// Main class
public class Linked_Hash_Map_Demo {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty LinkedHashMap
        LinkedHashMap<String, Integer> li_hash_map
            = new LinkedHashMap<String, Integer>();

        // Mapping int values to string keys
        // using put() method
        li_hash_map.put("Geeks", 10);
        li_hash_map.put("4", 15);
        li_hash_map.put("Geeks", 20);
        li_hash_map.put("Welcomes", 25);
        li_hash_map.put("You", 30);

        // Printing all elements of LinkedHashMap
        System.out.println("Initial Mappings are: "
                           + li_hash_map);

        // Getting the value of "Geeks"
        System.out.println("The Value is: "
                           + li_hash_map.get("Geeks"));

        // Getting the value of "You"
        System.out.println("The Value is: "
                           + li_hash_map.get("You"));
    }
}
```

**Output:** 

```
Initial Mappings are: {Geeks=20, 4=15, Welcomes=25, You=30}
The Value is: 20
The Value is: 30
```

> **注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。