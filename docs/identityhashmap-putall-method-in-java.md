# Java 中的 IdentityHashMap putAll()方法

> 原文:[https://www . geeksforgeeks . org/identityhashmap-putall-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-putall-method-in-java/)

Java . util . IdentityHashMap . putall()是用于复制操作的 identity hashmap 类的内置方法。该方法将所有元素(即映射)从一个映射复制到另一个映射。

**语法:**

```java
new_Identityhash_map.putAll(*exist_Identityhash_map*)
```

**参数:**该方法取一个参数 *exist_Identityhash_map* ，指的是我们要复制的现有地图。

**返回值:**该方法不返回值。

**异常:**如果我们要复制的地图为空，该方法抛出*空指针异常*。

下面的程序说明了 Java . util . identity hashmap . putall()方法的工作原理:
**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the putAll() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<Integer, String> Identity_hash = new 
                      IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        Identity_hash.put(10, "Geeks");
        Identity_hash.put(15, "4");
        Identity_hash.put(20, "Geeks");
        Identity_hash.put(25, "Welcomes");
        Identity_hash.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: " + 
                                           Identity_hash);

        // Creating a new Identityhash map and copying
        Map<Integer, String> new_Identityhash_map = new 
                        IdentityHashMap<Integer, String>();
        new_Identityhash_map.putAll(Identity_hash);

        // Displaying the final IdentityHashMap
        System.out.println("The new map: " + 
                                    new_Identityhash_map);
    }
}
```

**Output:**

```java
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
The new map: {15=4, 30=You, 10=Geeks, 25=Welcomes, 20=Geeks}

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the putAll() method
import java.util.*;

public class IdentityHash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<String, Integer> Identity_hash = new 
                      IdentityHashMap<String, Integer>();

        // Mapping int values to string keys
        Identity_hash.put("Geeks", 10);
        Identity_hash.put("4", 15);
        Identity_hash.put("Geeks", 20);
        Identity_hash.put("Welcomes", 25);
        Identity_hash.put("You", 30);

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: " + 
                                          Identity_hash);

        // Creating a new Identityhash map and copying
        Map<String, Integer> new_Identityhash_map = new 
                      IdentityHashMap<String, Integer>();
        new_Identityhash_map.putAll(Identity_hash);

        // Displaying the final IdentityHashMap
        System.out.println("The new map: " + 
                                   new_Identityhash_map);
    }
}
```

**Output:**

```java
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
The new map: {Welcomes=25, 4=15, You=30, Geeks=20}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。