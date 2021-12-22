# Java 中的 IdentityHashMap remove()方法

> 原文:[https://www . geesforgeks . org/identityhashmap-remove-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-remove-method-in-java/)

Java . util . IdentityHashMap . remove()是 identity hashmap 类的内置方法，用于从映射中移除任何特定键的映射。它基本上删除了地图中任何特定键的值。

**语法:**

```
Identity_Hash_Map.remove(*Object key*)
```

**参数:**该方法采用一个参数*键*，其映射将从地图中移除。

**返回值:**该方法返回之前映射到指定键的值，如果该键存在，则该方法返回空值。

下面的程序说明了 Java . util . identity hashmap . remove()方法的工作方式:
**程序 1:** 当传递一个现有的密钥时。

```
// Java code to illustrate the remove() method
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

        // Removing the existing key mapping
        String returned_value = 
                         (String)Identity_hash.remove(20);

        // Verifying the returned value
        System.out.println("Returned value is: " + 
                                      returned_value);

        // Displayin the new map
        System.out.println("New map is: " + Identity_hash);
    }
}
```

**Output:**

```
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
Returned value is: Geeks
New map is: {30=You, 15=4, 10=Geeks, 25=Welcomes}

```

**程序 2:** 传递新密钥时。

```
// Java code to illustrate the remove() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<Integer, String> Identity_hash = 
                   new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        Identity_hash.put(10, "Geeks");
        Identity_hash.put(15, "4");
        Identity_hash.put(20, "Geeks");
        Identity_hash.put(25, "Welcomes");
        Identity_hash.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: " + 
                                          Identity_hash);

        // Removing the new key mapping
        String returned_value = 
                        (String)Identity_hash.remove(50);

        // Verifying the returned value
        System.out.println("Returned value is: " + 
                                    returned_value);

        // Displayin the new map
        System.out.println("New map is: "+Identity_hash);
    }
}
```

**Output:**

```
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
Returned value is: null
New map is: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。