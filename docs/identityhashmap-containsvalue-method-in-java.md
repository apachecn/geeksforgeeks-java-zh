# Java 中的 IdentityHashMap containsValue()方法

> 原文:[https://www . geesforgeks . org/identity hashmap-contains value-method-in-Java/](https://www.geeksforgeeks.org/identityhashmap-containsvalue-method-in-java/)

Java . util . IdentityHashMap . contains value()方法用于检查特定值是由 identity hashmap 中的一个键映射还是由多个键映射。它将值作为参数，如果该值由映射中的任何键映射，则返回真。

**语法:**

```java
Identity_HashMap.containsValue(*Object Value*)
```

**参数:**该方法只取一个对象类型的参数*值*，并引用其映射应该由映射内任何键检查的值。

**返回值:**如果检测到值的映射，则该方法返回布尔值 true，否则返回 false。

下面的程序说明了 Java . util . identity hashmap . contains value()方法:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the containsValue() method
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

        // Checking for the Value 'Geeks'
        System.out.println("Is the value 'Geeks' present? " + 
                        identity_hash.containsValue("Geeks"));

        // Checking for the Value 'World'
        System.out.println("Is the value 'World' present? " + 
                        identity_hash.containsValue("World"));
    }
}
```

**输出:**

```java
Initial Mappings are: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
Is the value 'Geeks' present? true
Is the value 'World' present? false

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the containsValue() method
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

        // Checking for the Value '10'
        System.out.println("Is the value '10' present? " + 
                           identity_hash.containsValue(10));

        // Checking for the Value '30'
        System.out.println("Is the value '30' present? " + 
                           identity_hash.containsValue(30));

        // Checking for the Value '40'
        System.out.println("Is the value '40' present? " + 
                          identity_hash.containsValue(40));
    }
}
```

**输出:**

```java
Initial Mappings are: {Geeks=20, Welcomes=25, You=30, 4=15}
Is the value '10' present? false
Is the value '30' present? true
Is the value '40' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。