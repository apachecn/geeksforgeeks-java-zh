# Java 中的 HashMap get()方法

> 原文:[https://www.geeksforgeeks.org/hashmap-get-method-in-java/](https://www.geeksforgeeks.org/hashmap-get-method-in-java/)

HashMap 类的 java.util.HashMap.get()方法用于检索或获取参数中提到的特定键映射的值。当映射不包含键的这种映射时，它返回空值。

**语法:**

```java
Hash_Map.get(*Object key_element*)
```

**参数:**该方法取一个对象类型的参数 *key_element* ，指的是应该取关联值的键。

**返回值:**该方法返回与参数中*键 _ 元素*相关联的值。

下面的程序说明了 java.util.HashMap.get()方法的工作原理:
**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the get() method
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

        // Getting the value of 25
        System.out.println("The Value is: " + hash_map.get(25));

        // Getting the value of 10
        System.out.println("The Value is: " + hash_map.get(10));
    }
}
```

**Output:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The Value is: Welcomes
The Value is: Geeks

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the get() method
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

        // Getting the value of "Geeks"
        System.out.println("The Value is: " + hash_map.get("Geeks"));

        // Getting the value of "You"
        System.out.println("The Value is: " + hash_map.get("You"));
    }
}
```

**Output:**

```java
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The Value is: 20
The Value is: 30

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。