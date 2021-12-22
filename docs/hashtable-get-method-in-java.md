# Java 中的 Hashtable get()方法

> 原文:[https://www.geeksforgeeks.org/hashtable-get-method-in-java/](https://www.geeksforgeeks.org/hashtable-get-method-in-java/)

[Hashtable 类](https://www.geeksforgeeks.org/java-util-hashtable-class-java/)的 java.util.Hashtable.get()方法用于检索或获取参数中提到的特定键映射的值。当表不包含这样的键映射时，它返回空值。

**语法:**

```
Hash_Table.get(*Object key_element*)
```

**参数:**该方法取一个对象类型的参数 *key_element* ，指的是应该取关联值的键。

**返回值:**该方法返回与参数中*键 _ 元素*相关联的值。

下面的程序说明了 java.util.Hashtable.get()方法的工作:
**程序 1:**

```
// Java code to illustrate the get() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<Integer, String> hash_table = 
                           new Hashtable<Integer, String>();

        // Inserting the values into table
        hash_table.put(10, "Geeks");
        hash_table.put(15, "4");
        hash_table.put(20, "Geeks");
        hash_table.put(25, "Welcomes");
        hash_table.put(30, "You");

        // Displaying the Hashtable
        System.out.println("Initial Table is: " + hash_table);

        // Getting the value of 25
        System.out.println("The Value is: " + hash_table.get(25));

        // Getting the value of 10
        System.out.println("The Value is: " + hash_table.get(10));
    }
}
```

**Output:**

```
Initial Table is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
The Value is: Welcomes
The Value is: Geeks

```

**程序 2:**

```
// Java code to illustrate the get() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<String, Integer> hash_table = 
                            new Hashtable<String, Integer>();

        // Inserting the values into table
        hash_table.put("Geeks", 10);
        hash_table.put("4", 15);
        hash_table.put("Geeks", 20);
        hash_table.put("Welcomes", 25);
        hash_table.put("You", 30);

        // Displaying the Hashtable
        System.out.println("Initial table is: " + hash_table);

        // Getting the value of "Geeks"
        System.out.println("The Value is: " + hash_table.get("Geeks"));

        // Getting the value of "You"
        System.out.println("The Value is: " + hash_table.get("You"));
    }
}
```

**Output:**

```
Initial table is: {You=30, Welcomes=25, 4=15, Geeks=20}
The Value is: 20
The Value is: 30

```

**注意:**相同的操作可以用任何类型的变异和不同数据类型的组合来执行。