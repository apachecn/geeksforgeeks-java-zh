# 哈希表包含 Java 中的()方法

> 原文:[https://www . geesforgeks . org/hashtable-contains-method-in-Java/](https://www.geeksforgeeks.org/hashtable-contains-method-in-java/)

java 中的 Java . util . Hashtable . contains(*Object value*)方法用于检查哈希表中存在的任何键是否正在映射特定的值。

**语法:**

```java
Hash_table.contains(*Object value*)
```

**参数:**该方法接受一个对象类型的参数*值*，并引用映射待验证的哈希表的值。

**返回值:**如果传递的*值*由哈希表中的任意键映射，则该方法返回布尔*真*值。

**异常:**如果传递的*值*为空，则该方法抛出*空指针异常*。

以下程序说明上述方法的工作:
**程序 1:**

```java
// Java code to illustrate the contains() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<Integer, String> hash_table = 
        new Hashtable<Integer, String>();

        // Mapping string values to int keys
        hash_table.put(10, "Geeks");
        hash_table.put(15, "4");
        hash_table.put(20, "Geeks");
        hash_table.put(25, "Welcomes");
        hash_table.put(30, "You");

        // Displaying the HashMap
        System.out.println("Initial Table is: " + hash_table);

        // Checking for the Value 'Geeks'
        System.out.println("Is the value 'Geeks' present? " + 
        hash_table.contains("Geeks"));

        // Checking for the Value 'World'
        System.out.println("Is the value 'World' present? " + 
        hash_table.contains("World"));
    }
}
```

**Output:**

```java
Initial Table is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
Is the value 'Geeks' present? true
Is the value 'World' present? false

```

**程序 2:**

```java
// Java code to illustrate the contains() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<String, Integer> hash_table = 
        new Hashtable<String, Integer>();

        // Mapping int values to string keys
        hash_table.put("Geeks", 10);
        hash_table.put("4", 15);
        hash_table.put("Geeks", 20);
        hash_table.put("Welcomes", 25);
        hash_table.put("You", 30);

        // Displaying the Hashtable
        System.out.println("Initial Mappings are: " + hash_table);

        // Checking for the Value '10'
        System.out.println("Is the value '10' present? " + 
        hash_table.containsValue(10));

        // Checking for the Value '30'
        System.out.println("Is the value '30' present? " + 
        hash_table.containsValue(30));

        // Checking for the Value '40'
        System.out.println("Is the value '40' present? " + 
        hash_table.containsValue(40));
    }
}
```

**Output:**

```java
Initial Mappings are: {You=30, Welcomes=25, 4=15, Geeks=20}
Is the value '10' present? false
Is the value '30' present? true
Is the value '40' present? false

```