# HashMap 包含 Java 中的 Value()方法

> 原文:[https://www . geesforgeks . org/hashmap-contains value-method-in-Java/](https://www.geeksforgeeks.org/hashmap-containsvalue-method-in-java/)

Java . util . HashMap . contains VaLue()方法用于检查特定值是由 HashMap 中的一个键映射还是由多个键映射。它将值作为参数，如果该值由映射中的任何键映射，则返回真。

**语法:**

```java
Hash_Map.containsValue(*Object Value*)
```

**参数:**该方法只取一个对象类型的参数*值*，并引用其映射应该由映射内任何键检查的值。

**返回值:**如果检测到值的映射，则该方法返回布尔值 true，否则返回 false。

下面的程序用来说明 Java . util . hashmap . contains value()方法:
**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the containsValue() method
import java.util.*;

public class Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty HashMap
        HashMap<Integer, String> hash_map = new HashMap<Integer, String>();

        // Mapping string values to int keys
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Displaying the HashMap
        System.out.println("Initial Mappings are: " + hash_map);

        // Checking for the Value 'Geeks'
        System.out.println("Is the value 'Geeks' present? " + 
        hash_map.containsValue("Geeks"));

        // Checking for the Value 'World'
        System.out.println("Is the value 'World' present? " + 
        hash_map.containsValue("World"));
    }
}
```

**Output:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Is the value 'Geeks' present? true
Is the value 'World' present? false

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the containsValue() method
import java.util.*;

public class Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty HashMap
        HashMap<String, Integer> hash_map = new HashMap<String, Integer>();

        // Mapping int values to string keys
        hash_map.put("Geeks", 10);
        hash_map.put("4", 15);
        hash_map.put("Geeks", 20);
        hash_map.put("Welcomes", 25);
        hash_map.put("You", 30);

        // Displaying the HashMap
        System.out.println("Initial Mappings are: " + hash_map);

        // Checking for the Value '10'
        System.out.println("Is the value '10' present? " +
        hash_map.containsValue(10));

        // Checking for the Value '30'
        System.out.println("Is the value '30' present? " +
        hash_map.containsValue(30));

        // Checking for the Value '40'
        System.out.println("Is the value '40' present? " + 
        hash_map.containsValue(40));
    }
}
```

**Output:**

```java
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
Is the value '10' present? false
Is the value '30' present? true
Is the value '40' present? false

```

 **时间复杂度:** O(n)

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。