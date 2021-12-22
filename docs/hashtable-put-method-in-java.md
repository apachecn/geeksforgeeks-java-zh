# Java 中的 Hashtable put()方法

> 原文:[https://www.geeksforgeeks.org/hashtable-put-method-in-java/](https://www.geeksforgeeks.org/hashtable-put-method-in-java/)

Hashtable 的 java.util.Hashtable.put()方法用于将映射插入到表中。这意味着我们可以将特定的键及其映射到的值插入到特定的表中。如果传递了一个现有的键，那么前一个值将被新值替换。如果传递了一个新的对，那么该对将作为一个整体被插入。

**语法:**

```
Hash_Table.put(*key, value*)
```

**参数:**该方法采用两个参数，都是哈希表的对象类型。

*   *键:*这是指需要插入到表中进行映射的键元素。
*   *值:*这是指上述键将映射到的值。

**返回值:**如果传递了一个现有的键，则返回前一个值。如果传递了新的对，则返回空值。

下面的程序用来说明 java.util.Hashtable.put()方法:
**程序 1:** 在传递现有密钥时的工作方式。

```
// Java code to illustrate the put() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<Integer, String> hash_table = 
                           new Hashtable<Integer, String>();

        // Inserting values into the table
        hash_table.put(10, "Geeks");
        hash_table.put(15, "4");
        hash_table.put(20, "Geeks");
        hash_table.put(25, "Welcomes");
        hash_table.put(30, "You");

        // Displaying the Hashtable
        System.out.println("Initial table is: " + hash_table);

        // Inserting existing key along with new value
        String returned_value = (String)hash_table.put(20, "All");

        // Verifying the returned value
        System.out.println("Returned value is: " + returned_value);

        // Displaying the new table
        System.out.println("New table is: " + hash_table);
    }
}
```

**Output:**

```
Initial table is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
Returned value is: Geeks
New table is: {10=Geeks, 20=All, 30=You, 15=4, 25=Welcomes}

```

**程序 2:** 传递新密钥时。

```
// Java code to illustrate the put() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<Integer, String> hash_table = 
                           new Hashtable<Integer, String>();

        // Inserting values into the table
        hash_table.put(10, "Geeks");
        hash_table.put(15, "4");
        hash_table.put(20, "Geeks");
        hash_table.put(25, "Welcomes");
        hash_table.put(30, "You");

        // Displaying the Hashtable
        System.out.println("Initial table is: " + hash_table);

        // Inserting existing key along with new value
        String returned_value = (String)hash_table.put(50, "All");

        // Verifying the returned value
        System.out.println("Returned value is: " + returned_value);

        // Displaying the new table
        System.out.println("New table is: " + hash_table);
    }
}
```

**Output:**

```
Initial table is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
Returned value is: null
New table is: {10=Geeks, 20=Geeks, 30=You, 50=All, 15=4, 25=Welcomes}

```

**注意:**相同的操作可以用任何类型的变异和不同数据类型的组合来执行。