# Java 中的 HashTable putIfAbsent()方法，带示例

> 原文:[https://www . geesforgeks . org/hashtable-putifabsent-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashtable-putifabsent-method-in-java-with-examples/)

**哈希表类**的 **putIfAbsent(Key，value)** 方法，如果给定的键不与值相关联或映射为空，则允许将值映射到给定的键。如果哈希表中已经存在这样的键值集，则返回空值。

**语法:**

```java
public V putIfAbsent(K key, V value)
```

**参数:**该方法接受两个参数:

*   **Key** : If the key is not associated with any value, specify the key to which the specified value is mapped.
*   **Value** : Specify the value to be mapped to the specified key.

**返回:**该方法返回**映射到键的现有值，如果之前没有值映射到键，则返回空值**。

**异常:**此方法抛出:

*   [T0】 null pointerexception 【T1]: when the specified parameter is empty.

下面的程序说明了 putIfAbsent(键，值)方法:

**程序 1:**

```java
// Java program to demonstrate
// putIfAbsent(key, value) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a table and add some values
        Map<String, Integer>
            table = new Hashtable<>();

        table.put("Pen", 10);
        table.put("Book", 500);
        table.put("Clothes", 400);
        table.put("Mobile", 5000);

        // print map details
        System.out.println("hashTable: "
                           + table.toString());

        // Inserting non-existing key with value
        // using putIfAbsent method
        String retValue
            = String.valueOf(table
                                 .putIfAbsent("Booklet", 2500));

        // Print the returned value
        System.out.println("Returned value "
                           + "for Key 'Booklet' is: "
                           + retValue);

        // print new mapping
        System.out.println("hashTable: "
                           + table);

        // Inserting existing key with value
        // using putIfAbsent method
        retValue
            = String.valueOf(table
                                 .putIfAbsent("Book", 4500));

        // Print the returned value
        System.out.println("Returned value"
                           + " for key 'Book' is: "
                           + retValue);

        // print new mapping
        System.out.println("hashTable: "
                           + table);
    }
}
```

**输出:**

```java
hashTable: {Book=500, Mobile=5000, Pen=10, Clothes=400}
Returned value for Key 'Booklet' is: null
hashTable: {Book=500, Mobile=5000, Pen=10, Clothes=400, Booklet=2500}
Returned value for key 'Book' is: 500
hashTable: {Book=500, Mobile=5000, Pen=10, Clothes=400, Booklet=2500}

```

**程序 2:** 显示空指针异常

```java
// Java program to demonstrate
// putIfAbsent(key, value) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a table and add some values
        Map<Integer, String>
            table = new Hashtable<>();

        table.put(1, "100RS");
        table.put(2, "500RS");
        table.put(3, "1000RS");

        // print map details
        System.out.println("hashTable: "
                           + table.toString());

        try {

            table.putIfAbsent(null, "8");
        }
        catch (NullPointerException e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

T5】输出:

```java
hashTable: {3=1000RS, 2=500RS, 1=100RS}
Exception: java.lang.NullPointerException

```

参考文献:[https://docs . Oracle . com/javase/8/docs/API/Java/util/Hashtable . html # putIfAbsent-K-V-](https://docs.oracle.com/javase/8/docs/api/java/util/Hashtable.html#putIfAbsent-K-V-)