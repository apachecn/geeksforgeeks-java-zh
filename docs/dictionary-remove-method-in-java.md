# Java 中的字典删除()方法

> 原文:[https://www . geesforgeks . org/dictionary-remove-method-in-Java/](https://www.geeksforgeeks.org/dictionary-remove-method-in-java/)

[字典类](https://www.geeksforgeeks.org/java-util-dictionary-class-java/)的 **remove()** 方法接受一个*键*作为参数，并移除映射到该键的相应值。

**语法:**

```java
public abstract V remove(Object key)
```

**参数:**该函数接受一个参数**键**，该键表示要从字典中删除的键及其映射。

**返回值:**该函数返回映射到**键**的值，如果**键**没有映射，则返回*空值*。

**异常:**如果作为参数传递的**键**为*空*，则函数不抛出**空指针异常**。

下面的程序说明了**Java . util . dictionary . remove()**方法的使用:

**程序 1:**

```java
// Java Program to illustrate
// java.util.Dictionary.remove() method

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Create a new hashtable
        Dictionary<Integer, String>
            d = new Hashtable<Integer, String>();

        // Insert elements in the hashtable
        d.put(1, "Geeks");
        d.put(2, "for");
        d.put(3, "Geeks");

        // Print the Dictionary
        System.out.println("\nDictionary: " + d);

        // Display the removed value
        System.out.println(d.remove(3)
                           + " has been removed");

        // Print the Dictionary
        System.out.println("\nDictionary: " + d);
    }
}
```

**输出:**

```java
Dictionary: {3=Geeks, 2=for, 1=Geeks}
Geeks has been removed

Dictionary: {2=for, 1=Geeks}

```

**程序二:**

```java
// Java Program to illustrate
// java.util.Dictionary.remove() method

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Create a new hashtable
        Dictionary<String, String> d = new Hashtable<String, String>();

        // Insert elements in the hashtable
        d.put("a", "GFG");
        d.put("b", "gfg");

        // Print the Dictionary
        System.out.println("\nDictionary: " + d);

        // Display the removed value
        System.out.println(d.remove("a")
                           + " has been removed");
        System.out.println(d.remove("b")
                           + " has been removed");

        // Print the Dictionary
        System.out.println("\nDictionary: " + d);

        // returns true
        if (d.isEmpty()) {
            System.out.println("Dictionary "
                               + "is empty");
        }
        else
            System.out.println("Dictionary "
                               + "is not empty");
    }
}
```

**输出:**

```java
Dictionary: {b=gfg, a=GFG}
GFG has been removed
gfg has been removed

Dictionary: {}
Dictionary is empty

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/dictionary . html # remove()](https://docs.oracle.com/javase/7/docs/api/java/util/Dictionary.html#remove(java.lang.Object))