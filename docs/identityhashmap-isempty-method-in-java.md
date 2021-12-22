# Java 中的 IdentityHashMap isEmpty()方法

> 原文:[https://www . geeksforgeeks . org/identityhashmap-isempty-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-isempty-method-in-java/)

IdentityHashMap 类的 Java . util . identity hashmap . isempty()方法用于检查映射是否为空。如果映射中没有键值对或映射，则该方法返回真，否则返回假。

**语法:**

```java
Identity_Hash_Map.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**如果映射为空或者不包含任何映射对，则该方法返回布尔值 true，否则返回布尔值 false。

下面的程序说明了 Java . util . identity hashmap . isempty()方法的工作原理:
**程序 1:** 将字符串值映射到整键。

```java
// Java code to illustrate the isEmpty() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<String, Integer> identity_hash = new 
                     IdentityHashMap<String, Integer>();

        // Mapping int values to string keys
        identity_hash.put("Geeks", 10);
        identity_hash.put("4", 15);
        identity_hash.put("Geeks", 20);
        identity_hash.put("Welcomes", 25);
        identity_hash.put("You", 30);

        // Displaying the IdentityHashMap
        System.out.println("The Mappings are: "+
                                      identity_hash);

        // Checking for the emptiness of Map
        System.out.println("Is the map empty? "+
                           identity_hash.isEmpty());
    }
}
```

**Output:**

```java
The Mappings are: {Geeks=20, Welcomes=25, You=30, 4=15}
Is the map empty? false

```

**程序 2:** 为空标识哈希映射

```java
// Java code to illustrate the isEmpty() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<String, Integer> identity_hash = new 
                  IdentityHashMap<String, Integer>();

        // Displaying the IdentityHashMap
        System.out.println("The Mappings are: "+
                                      identity_hash);

        // Checking for the emptiness of Map
        System.out.println("Is the map empty? "+
                            identity_hash.isEmpty());
    }
}
```

**Output:**

```java
The Mappings are: {}
Is the map empty? true

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

[Java.util.IdentityHashMap 类](https://www.geeksforgeeks.org/java-util-IdentityHashMap-class-java/)的所有方法