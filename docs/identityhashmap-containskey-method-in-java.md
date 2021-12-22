# Java 中的 IdentityHashMap containsKey()方法

> 原文:[https://www . geesforgeks . org/identity hashmap-contains key-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-containskey-method-in-java/)

Java . util . IdentityHashMap . contains KeY()方法用于检查特定键是否映射到 identity hashmap。它将关键元素作为参数，如果该元素在映射中被映射，则返回 True。

**语法:**

```java
Identity_HashMap.containsKey(*key_element*)
```

**参数:**该方法只取一个参数 *key_element* ，该参数是指映射应该在地图内部检查的键。

**返回值:**如果检测到键的存在，则该方法返回布尔值 true，否则返回 false。

下面的程序用来说明 Java . util . identity hashmap . contains key()方法:
**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the containsKey() method
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

        // Checking for the key_element '20'
        System.out.println("Is the key '20' present? " + 
                           identity_hash.containsKey(20));

        // Checking for the key_element '5'
        System.out.println("Is the key '5' present? " + 
                            identity_hash.containsKey(5));
    }
}
```

**Output:**

```java
Initial Mappings are: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
Is the key '20' present? true
Is the key '5' present? false

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the containsKey() method
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

        // Checking for the key_element 'Welcomes'
        System.out.println("Is the key 'Welcomes' present? " + 
                        identity_hash.containsKey("Welcomes"));

        // Checking for the key_element 'World'
        System.out.println("Is the key 'World' present? " + 
                           identity_hash.containsKey("World"));
    }
}
```

**Output:**

```java
Initial Mappings are: {Geeks=20, Welcomes=25, You=30, 4=15}
Is the key 'Welcomes' present? true
Is the key 'World' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。