# Java 中的 Hashtable containsKey()方法

> 原文:[https://www . geesforgeks . org/hashtable-contains key-method-in-Java/](https://www.geeksforgeeks.org/hashtable-containskey-method-in-java/)

Java . util . Hashtable . Contains KeY()方法用于检查哈希表中是否存在特定的键。它将键元素作为参数，如果表中存在该元素，则返回 True。

**语法:**

```java
Hash_table.containsKey(*key_element*)
```

**参数:**该方法只取一个参数 *key_element* ，它指的是应该在哈希表中检查其存在的键。

**返回值:**如果键存在于哈希表中，该方法返回布尔真，否则返回假。

下面的程序用来说明 Java . util . hashtable . contains key()方法:
**程序 1:**

```java
// Java code to illustrate the containsKey() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<Integer, String> hash_table = 
        new Hashtable<Integer, String>();

        // Putting values into the table
        hash_table.put(10, "Geeks");
        hash_table.put(15, "4");
        hash_table.put(20, "Geeks");
        hash_table.put(25, "Welcomes");
        hash_table.put(30, "You");

        // Displaying the Hashtable
        System.out.println("Initial Table is: " + hash_table);

        // Checking for the key_element '20'
        System.out.println("Is the key '20' present? " + 
        hash_table.containsKey(20));

        // Checking for the key_element '5'
        System.out.println("Is the key '5' present? " + 
        hash_table.containsKey(5));
    }
}
```

**Output:**

```java
Initial Table is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
Is the key '20' present? true
Is the key '5' present? false

```

**程序 2:**

```java
// Java code to illustrate the containsKey() method
import java.util.*;

public class Hash_Table_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<String, Integer> hash_table= 
        new Hashtable<String, Integer>();

        // Putting values into the table
        hash_table.put("Geeks", 10);
        hash_table.put("4", 15);
        hash_table.put("Geeks", 20);
        hash_table.put("Welcomes", 25);
        hash_table.put("You", 30);

        // Displaying the Hashtable
        System.out.println("Initial Table is: " + hash_table);

        // Checking for the key_element 'Welcomes'
        System.out.println("Is the key 'Welcomes' present? " + 
        hash_table.containsKey("Welcomes"));

        // Checking for the key_element 'World'
        System.out.println("Is the key 'World' present? " + 
        hash_table.containsKey("World"));
    }
}
```

**Output:**

```java
Initial Table is: {You=30, Welcomes=25, 4=15, Geeks=20}
Is the key 'Welcomes' present? true
Is the key 'World' present? false

```

**注意:**相同的操作可以用任何类型的变异和不同数据类型的组合来执行。