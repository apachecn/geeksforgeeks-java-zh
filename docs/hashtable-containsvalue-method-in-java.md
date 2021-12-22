# Java 中的哈希表 containsValue()方法

> 原文:[https://www . geesforgeks . org/hashtable-contains value-method-in-Java/](https://www.geeksforgeeks.org/hashtable-containsvalue-method-in-java/)

Java . util . Hashtable . Contains VaLue()方法用于检查哈希表中的一个或多个键是否映射了特定的值。它将值作为参数，如果该值由表中的任何键映射，则返回真。

**语法:**

```
Hash_Table.containsValue(*Object Value*)
```

**参数:**该方法只取一个对象类型的参数*值*，并引用其映射应该由表内任何键检查的值。

**返回值:**如果值被映射到哈希表中的任何键，则该方法返回布尔值 true，否则返回 false。

以下程序用于说明 Java . util . hashtable . contains value()方法:
**程序 1:**

```
// Java code to illustrate the containsValue() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<Integer, String> hash_table = 
        new Hashtable<Integer, String>();

        // Putting values in the table
        hash_table.put(10, "Geeks");
        hash_table.put(15, "4");
        hash_table.put(20, "Geeks");
        hash_table.put(25, "Welcomes");
        hash_table.put(30, "You");

        // Displaying the Hashtable
        System.out.println("Initial Table is: " + hash_table);

        // Checking for the Value 'Geeks'
        System.out.println("Is the value 'Geeks' present? " + 
        hash_table.containsValue("Geeks"));

        // Checking for the Value 'World'
        System.out.println("Is the value 'World' present? " + 
        hash_table.containsValue("World"));
    }
}
```

**Output:**

```
Initial Table is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
Is the value 'Geeks' present? true
Is the value 'World' present? false

```

**程序 2:**

```
// Java code to illustrate the containsValue() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<String, Integer> hash_table = 
        new Hashtable<String, Integer>();

        // Putting values in the table
        hash_table.put("Geeks", 10);
        hash_table.put("4", 15);
        hash_table.put("Geeks", 20);
        hash_table.put("Welcomes", 25);
        hash_table.put("You", 30);

        // Displaying the Hashtable
        System.out.println("Initial Table is: " + hash_table);

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

```
Initial Table is: {You=30, Welcomes=25, 4=15, Geeks=20}
Is the value '10' present? false
Is the value '30' present? true
Is the value '40' present? false

```

**注意:**相同的操作可以用任何类型的变异和不同数据类型的组合来执行。