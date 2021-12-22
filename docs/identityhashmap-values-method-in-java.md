# Java 中的 IdentityHashMap 值()方法

> 原文:[https://www . geesforgeks . org/identityhashmap-values-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-values-method-in-java/)

java 中 IdentityHashMap 类的 Java . util . identity hashmap . values()方法用于从映射的值中创建一个集合。它基本上返回地图中值的集合视图。

**语法:**

```
Identity_Hash_Map.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法用于返回包含地图所有值的集合视图。

以下程序用于说明 Java . util . identity hashmap . values()方法:
**程序 1:**

```
// Java code to illustrate the values() method
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

        // Using values() to get the set view of values
        System.out.println("The collection is: " + 
                                   Identity_hash.values());
    }
}
```

**Output:**

```
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
The collection is: [You, 4, Geeks, Welcomes, Geeks]

```

**程序 2:**

```
// Java code to illustrate the values() method
import java.util.*;

public class Identity_Hash_Map_Demo {
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

        // Using values() to get the set view of values
        System.out.println("The collection is: " + 
                                   Identity_hash.values());
    }
}
```

**Output:**

```
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
The collection is: [25, 15, 30, 20]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。