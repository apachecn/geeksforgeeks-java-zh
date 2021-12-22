# Java 中 IdentityHashMap size()方法

> 原文:[https://www . geesforgeks . org/identityhashmap-size-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-size-method-in-java/)

IdentityHashMap 类的 java.util.IdentityHashMap.size()方法用于获取 IdentityHashMap 的大小，该大小是指映射中键值对或映射的数量。

**语法:**

```java
Identity_Hash_Map.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回地图的大小，这也意味着地图中存在的键值对的数量。

下面的程序说明了 java.util.IdentityHashMap.size()方法:

**节目 1** :

```java
// Java code to illustrate the size() method
import java.util.*;

public class Identity_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<Integer, String> identity_hash = new 
                      IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        identity_hash.put(10, "Geeks");
        identity_hash.put(15, "4");
        identity_hash.put(20, "Geeks");
        identity_hash.put(25, "Welcomes");
        identity_hash.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: " + 
                                           identity_hash);

        // Displaying the size of the map
        System.out.println("The size of the map is " + 
                                    identity_hash.size());
    }
}
```

**输出:**

```java
Initial Mappings are: {Geeks=20, Welcomes=25, You=30, 4=15}
The size of the map is 4
```

**节目 2:**

```java
// Java code to illustrate the size() method
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
        System.out.println("Initial Mappings are: " + 
                                           identity_hash);

        // Displaying the size of the map
        System.out.println("The size of the map is " + 
                                     identity_hash.size());
    }
}
```

**输出:**

```java
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
The size of the map is 4
```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。