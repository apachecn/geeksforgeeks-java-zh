# Java 中的 Hashtable toString()方法

> 原文:[https://www . geesforgeks . org/hashtable-tostring-method-in-Java/](https://www.geeksforgeeks.org/hashtable-tostring-method-in-java/)

java.util.Hashtable.toString()是 Hashtable 的一种内置方法，用于获取 Hashtable 对象的字符串表示形式，即以“，”分隔的一组条目。所以基本上 toString()方法是用来把 Hashtable 的所有元素转换成 String。
**语法:**

```
Hash_Table.toString()
```

**参数:**该方法不取任何参数。
**返回值:**该方法返回由哈希表元素的字符串表示组成的集合。
以下程序说明了 java.util.Hashtable.toString()方法的工作:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the toString() method
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

        // Displaying the string representation
        System.out.println("The set is: " + hash_table.toString());
    }
}
```

**Output:** 

```
Initial table is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
The set is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the toString() method
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

        // Displaying the string representation
        System.out.println("The set is: " + hash_table.toString());
    }
}
```

**Output:** 

```
Initial Table is: {You=30, Welcomes=25, 4=15, Geeks=20}
The set is: {You=30, Welcomes=25, 4=15, Geeks=20}
```