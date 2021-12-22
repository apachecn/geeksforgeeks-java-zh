# Java 中的 IdentityHashMap entrySet()方法

> 原文:[https://www . geesforgeks . org/identityhashmap-entryset-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-entryset-method-in-java/)

java 中的 Java . util . identity hashmap . entryset()方法用于创建一组包含在映射中的相同元素。它基本上返回身份哈希映射的集合视图，或者我们可以创建一个新的集合并将映射元素存储到其中。

**语法:**

```
Identity_HashMap.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与地图元素相同的集合。

下面的程序说明了 Java . util . identity hashmap . entryset()方法:
**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the entrySet() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        IdentityHashMap<Integer, String> identity_hash = 
                      new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        identity_hash.put(10, "Geeks");
        identity_hash.put(15, "4");
        identity_hash.put(20, "Geeks");
        identity_hash.put(25, "Welcomes");
        identity_hash.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: " + 
                                             identity_hash);

        // Using entrySet() to get the set view
        System.out.println("The set is: " + 
                                   identity_hash.entrySet());
    }
}
```

**Output:**

```
Initial Mappings are: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
The set is: [10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4]

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the entrySet() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        IdentityHashMap<String, Integer> identity_hash = 
                       new IdentityHashMap<String, Integer>();

        // Mapping int values to string keys
        identity_hash.put("Geeks", 10);
        identity_hash.put("4", 15);
        identity_hash.put("Geeks", 20);
        identity_hash.put("Welcomes", 25);
        identity_hash.put("You", 30);

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: " + 
                                               identity_hash);

        // Using entrySet() to get the set view
        System.out.println("The set is: " + 
                                   identity_hash.entrySet());
    }
}
```

**Output:**

```
Initial Mappings are: {Geeks=20, Welcomes=25, You=30, 4=15}
The set is: [Geeks=20, Welcomes=25, You=30, 4=15]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。