# Java 中的 Hashtable clear()方法

> 原文:[https://www . geesforgeks . org/hashtable-clear-method-in-Java/](https://www.geeksforgeeks.org/hashtable-clear-method-in-java/)

java 中的 java.util.Hashtable.clear()方法用于清除和移除指定 Hashtable 中的所有键。

**语法:**

```java
Hash_table.clear()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

下面的程序用来说明 java.util.Hashtable.clear()方法:
**程序 1:**

```java
// Java code to illustrate the clear() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<Integer, String> hash_table = new Hashtable<Integer, String>();

        // Inserting Values into table
        hash_table.put(10, "Geeks");
        hash_table.put(15, "4");
        hash_table.put(20, "Geeks");
        hash_table.put(25, "Welcomes");
        hash_table.put(30, "You");

        // Displaying the Hashtable
        System.out.println("The Hashtable is: " + hash_table);

        // Clearing the hash table using clear()
        hash_table.clear();

        // Displaying the final Hashtable
        System.out.println("Finally the table looks like this: " + hash_table);
    }
}
```

**Output:**

```java
The Hashtable is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
Finally the table looks like this: {}

```

**程序 2:**

```java
// Java code to illustrate the clear() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<String, Integer> hash_table = new Hashtable<String, Integer>();

        // Inserting Values into table
        hash_table.put("Geeks", 10);
        hash_table.put("4", 15);
        hash_table.put("Geeks", 20);
        hash_table.put("Welcomes", 25);
        hash_table.put("You", 30);

        // Displaying the Hashtable
        System.out.println("The Hashtable is: " + hash_table);

        // Clearing the hash table using clear()
        hash_table.clear();

        // Displaying the final Hashtable
        System.out.println("Finally the table looks like this: " + hash_table);
    }
}
```

**Output:**

```java
The Hashtable is: {You=30, Welcomes=25, 4=15, Geeks=20}
Finally the table looks like this: {}

```

**注意:**相同的操作可以用任何类型的变异和不同数据类型的组合来执行。