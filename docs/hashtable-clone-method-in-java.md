# Java 中的哈希表克隆()方法

> 原文:[https://www . geesforgeks . org/hashtable-clone-method-in-Java/](https://www.geeksforgeeks.org/hashtable-clone-method-in-java/)

java.util.Hashtable.clone()方法用于返回上述哈希表的浅层副本。它只是创建了一个表的副本。

**语法:**

```java
Hash_Table.clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法只返回哈希表的一个副本。

下面的程序用来说明 java.util.Hashtable.clone()方法:
**程序 1:**

```java
// Java code to illustrate the clone() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {
        // Creating an empty Hashtable
        Hashtable<Integer, String> hash_table = new Hashtable<Integer, String>();

        // Putting values into the table
        hash_table.put(10, "Geeks");
        hash_table.put(15, "4");
        hash_table.put(20, "Geeks");
        hash_table.put(25, "Welcomes");
        hash_table.put(30, "You");

        // Displaying the Hashtable
        System.out.println("The Hashtable is: " + hash_table);

        // Displaying the cloned Hashtable using clone()
        System.out.println("The cloned table look like this: "
                           + hash_table.clone());
    }
}
```

**Output:**

```java
The Hashtable is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
The cloned table look like this: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}

```

**程序 2:**

```java
// Java code to illustrate the clone() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {
        // Creating an empty Hashtable
        Hashtable<String, Integer> hash_table = new Hashtable<String, Integer>();

        // Putting Values into the table
        hash_table.put("Geeks", 10);
        hash_table.put("4", 15);
        hash_table.put("Geeks", 20);
        hash_table.put("Welcomes", 25);
        hash_table.put("You", 30);

        // Displaying the Hashtable
        System.out.println("The Hashtable is: " + hash_table);

        // Displaying the cloned Hashtable using clone()
        System.out.println("The cloned table look like this: "
                           + hash_table.clone());
    }
}
```

**Output:**

```java
The Hashtable is: {You=30, Welcomes=25, 4=15, Geeks=20}
The cloned table look like this: {You=30, Welcomes=25, 4=15, Geeks=20}

```

**注意:**相同的操作可以用任何类型的变异和不同数据类型的组合来执行。