# Java 中的 Hashtable isEmpty()方法

> 原文:[https://www . geesforgeks . org/hashtable-isempty-method-in-Java/](https://www.geeksforgeeks.org/hashtable-isempty-method-in-java/)

Hashtable 类的 java.util.Hashtable.isEmpty()方法用于检查表的空性。如果表中没有键值对或映射，则该方法返回真，否则返回假。

**语法:**

```
Hash_Table.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**如果表为空或不包含任何映射对，则该方法返回布尔值 true，否则返回布尔值 false。

下面的程序说明了 java.util.Hashtable.isEmpty()方法的工作:
**程序 1:**

```
// Java code to illustrate the isEmpty() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<String, Integer> hash_table = 
                       new Hashtable<String, Integer>();

        // Inserting elements into the table
        hash_table.put("Geeks", 10);
        hash_table.put("4", 15);
        hash_table.put("Geeks", 20);
        hash_table.put("Welcomes", 25);
        hash_table.put("You", 30);

        // Displaying the Hashtable
        System.out.println("The table is: " + hash_table);

        // Checking for the emptiness of Table
        System.out.println("Is the table empty? " + 
                                 hash_table.isEmpty());
    }
}
```

**Output:**

```
The table is: {You=30, Welcomes=25, 4=15, Geeks=20}
Is the table empty? false

```

**程序 2:**

```
// Java code to illustrate the isEmpty() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<String, Integer> hash_table = new Hashtable<String, Integer>();

        // Displaying the Hashtable
        System.out.println("The table is: " + hash_table);

        // Checking for the emptiness of Table
        System.out.println("Is the table empty? " + hash_table.isEmpty());
    }
}
```

**Output:**

```
The table is: {}
Is the table empty? true

```

**注意:**相同的操作可以用任何类型的变异和不同数据类型的组合来执行。