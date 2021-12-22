# Java 中的哈希表元素()方法

> 原文:[https://www . geesforgeks . org/hashtable-elements-method-in-Java/](https://www.geeksforgeeks.org/hashtable-elements-method-in-java/)

java 中 Hashtable 类的 java.util.Hashtable.elements()方法用于获取 Hashtable 中存在的值的枚举。

**语法:**

```java
Enumeration enu = Hash_table.elements()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回哈希表值的枚举。

下面的程序用来说明 java.util.Hashtable.elements()方法的工作:
**程序 1:**

```java
// Java code to illustrate the elements() method
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
        System.out.println("The Table is: " + hash_table);

        // Creating an empty enumeration to store
        Enumeration enu = hash_table.elements();

        System.out.println("The enumeration of values are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**Output:**

```java
The Table is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
The enumeration of values are:
Geeks
Geeks
You
4
Welcomes

```

**程序二:**

```java
// Java code to illustrate the elements() method
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
        System.out.println("The Table is: " + hash_table);

        // Creating an empty enumeration to store
        Enumeration enu = hash_table.elements();

        System.out.println("The enumeration of values are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

****输出:**

```java
The Table is: {You=30, Welcomes=25, 4=15, Geeks=20}
The enumeration of values are:
30
25
15
20

```**