# Java 中的 IdentityHashMap get()方法

> 原文:[https://www . geesforgeks . org/identityhashmap-get-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-get-method-in-java/)

IdentityHashMap 类的 java.util.IdentityHashMap.get()方法用于检索或获取参数中提到的特定键映射的值。当映射不包含键的这种映射时，它返回空值。

**语法:**

```java
IdentityHashMap.get(*Object key_element*)
```

**参数:**该方法取一个对象类型的参数 *key_element* ，指的是应该取关联值的键。

**返回值:**该方法返回与参数中*键 _ 元素*相关联的值。

下面的程序说明了 java.util.IdentityHashMap.get()方法的工作原理:

**程序 1:**

```java
// Java code to illustrate the get() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<Integer, String> identity_hash = 
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

        // Getting the value of 25
        System.out.println("The Value is: " + 
                                identity_hash.get(25));

        // Getting the value of 10
        System.out.println("The Value is: " + 
                                identity_hash.get(10));
    }
}
```

**输出:**

```java
Initial Mappings are: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
The Value is: Welcomes
The Value is: Geeks

```

**程序二:**

```java
// Java code to illustrate the get() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<String, Integer> identity_hash = 
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

        // Getting the value of "Geeks"
        System.out.println("The Value is: " + 
                          identity_hash.get("Geeks"));

        // Getting the value of "You"
        System.out.println("The Value is: " + 
                            identity_hash.get("You"));
    }
}
```

**输出:**

```java
Initial Mappings are: {Geeks=20, Welcomes=25, You=30, 4=15}
The Value is: 20
The Value is: 30

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。