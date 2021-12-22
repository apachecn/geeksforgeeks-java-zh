# Java 中 IdentityHashMap clear()方法

> 原文:[https://www . geesforgeks . org/identityhashmap-clear-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-clear-method-in-java/)

java 中的 Java . util . identity hashmap . clear()方法用于清除和移除指定映射中的所有元素或映射。

**语法:**

```
Identity_HashMap.clear()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

下面的程序用来说明 Java . util . identityhashmap . clear()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the clear() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        IdentityHashMap<Integer, String> identity_hash = new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        identity_hash.put(10, "Geeks");
        identity_hash.put(15, "4");
        identity_hash.put(20, "Geeks");
        identity_hash.put(25, "Welcomes");
        identity_hash.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: "
                           + identity_hash);

        // Clearing the map using clear()
        identity_hash.clear();

        // Displaying the final IdentityHashMap
        System.out.println("Final Map: "
                           + identity_hash);
    }
}
```

**输出:**

```
Initial Mappings are: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
Final Map: {}

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the clear() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<String, Integer> identity_hash = new IdentityHashMap<String, Integer>();

        // Mapping int values to string keys
        identity_hash.put("Geeks", 10);
        identity_hash.put("4", 15);
        identity_hash.put("Geeks", 20);
        identity_hash.put("Welcomes", 25);
        identity_hash.put("You", 30);

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: " + identity_hash);

        // Clearing the map using clear()
        identity_hash.clear();

        // Displaying the final IdentityHashMap
        System.out.println("Final Map: "
                           + identity_hash);
    }
}
```

**输出:**

```
Initial Mappings are: {Geeks=20, Welcomes=25, You=30, 4=15}
Final Map: {}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。