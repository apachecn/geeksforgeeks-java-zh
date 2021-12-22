# Java 中的 HashMap putAll()方法

> 原文:[https://www . geesforgeks . org/hashmap-pull-method-in-Java/](https://www.geeksforgeeks.org/hashmap-putall-method-in-java/)

java.util.HashMap.putAll()是 HashMap 类的一个内置方法，用于复制操作。该方法将所有元素(即映射)从一个映射复制到另一个映射。

**语法:**

```java
new_hash_map.putAll(*exist_hash_map*)
```

**参数:**方法取一个参数 *exist_hash_map* ，指的是我们要复制的现有地图。

**返回值:**该方法不返回值。

**异常:**如果我们要复制的地图为空，该方法抛出*空指针异常*。

下面的程序说明了 java.util.HashMap.putAll()方法的工作原理:
**程序 1:** 将字符串值映射到整键。

```java
// Java code to illustrate the putAll() method
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

    // Creating a new hash map and copying
    HashMap<Integer, String> new_hash_map = new HashMap<Integer, String>();
    new_hash_map.putAll(hash_map);

    // Displaying the final HashMap
    System.out.println("The new map looks like this: " + new_hash_map);
}
}
```

**Output:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The new map looks like this: {25=Welcomes, 10=Geeks, 20=Geeks, 30=You, 15=4}

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the putAll() method
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

        // Creating a new hash map and copying
        HashMap<String, Integer> new_hash_map = new HashMap<String, Integer>();
        new_hash_map.putAll(hash_map);

        // Displaying the final HashMap
        System.out.println("The new map looks like this: " + new_hash_map);
    }
}
```

**Output:**

```java
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The new map looks like this: {Geeks=20, 4=15, You=30, Welcomes=25}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。