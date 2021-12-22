# Java 中的 IdentityHashMap 克隆()方法

> 原文:[https://www . geesforgeks . org/identityhashmap-clone-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-clone-method-in-java/)

Java . util . identity hashmap . clone()方法用于返回上述哈希映射的浅层副本。它只是创建了一个地图的副本。

**语法:**

```java
Identity_HashMap.clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法只返回哈希映射的副本。

以下程序用于说明 Java . util . identity hashmap . clone()方法:
**程序 1:**

```java
// Java code to illustrate the clone() method
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

        // Displaying the cloned Map using clone()
        System.out.println("The cloned map: " + 
                                    identity_hash.clone());
    }
}
```

**Output:**

```java
Initial Mappings are: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
The cloned map: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}

```

**程序 2:**

```java
// Java code to illustrate the clone() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty hash map
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

        // Displaying the cloned map using clone()
        System.out.println("The cloned map: " + 
                                 identity_hash.clone());
    }
}
```

**Output:**

```java
Initial Mappings are: {Geeks=20, Welcomes=25, You=30, 4=15}
The cloned map: {Geeks=20, Welcomes=25, You=30, 4=15}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。