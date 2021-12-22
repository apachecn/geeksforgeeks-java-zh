# Java 中的哈希表大小()方法

> 原文:[https://www . geesforgeks . org/hashtable-size-method-in-Java/](https://www.geeksforgeeks.org/hashtable-size-method-in-java/)

Hashtable 类的 java.util.Hashtable.size()方法用于获取表的大小，表的大小是指表中键值对或映射的数量。

**语法:**

```
Hash_Table.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回表的大小，这也意味着表中存在的键值对的数量。

下面的程序说明了 Java . util . hashtable . size():
**程序 1:**

```
// Java code to illustrate the size() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<Integer, String> hash_table = 
        new Hashtable<Integer, String>();

        // Inserting elements into the table
        hash_table.put(10, "Geeks");
        hash_table.put(15, "4");
        hash_table.put(20, "Geeks");
        hash_table.put(25, "Welcomes");
        hash_table.put(30, "You");

        // Displaying the Hashtable
        System.out.println("Initial table is: " + hash_table);

        // Displaying the size of the table
        System.out.println("The size of the table is " + 
        hash_table.size());
    }
}
```

**Output:**

```
Initial table is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
The size of the table is 5

```

**程序 2:**

```
// Java code to illustrate the size() method
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
        System.out.println("Initial Table is: " + hash_table);

        // Displaying the size of the table
        System.out.println("The size of the table is " + 
        hash_table.size());
    }
}
```

**Output:**

```
Initial Table is: {You=30, Welcomes=25, 4=15, Geeks=20}
The size of the table is 4

```

**注意:**相同的操作可以用任何类型的变异和不同数据类型的组合来执行。