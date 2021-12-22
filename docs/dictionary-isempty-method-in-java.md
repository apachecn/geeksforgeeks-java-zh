# Java 中的字典 isEmpty()方法

> 原文:[https://www . geesforgeks . org/dictionary-isempty-method-in-Java/](https://www.geeksforgeeks.org/dictionary-isempty-method-in-java/)

[字典类](https://www.geeksforgeeks.org/java-util-dictionary-class-java/)的 **isEmpty()** 方法检查*这个*字典是否有键值映射。只有当*本*词典中没有条目时，该功能才返回*真*。

**语法:**

```java
public abstract boolean isEmpty()
```

**返回值:**如果字典为空，则函数返回*真*，否则返回*假*。

**异常:**函数没有抛出异常。

以下程序说明了**字典的使用方法:**

**程序 1:**

```java
// Java Program to illustrate
// Dictionary.isEmpty() method

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

        // check if this dictionary is empty
        // using isEmpty() method
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
Dictionary: {3=Geeks, 2=for, 1=Geeks}
Dictionary is not empty

```

**程序二:**

```java
// Java Program to illustrate
// Dictionary.isEmpty() method

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a new hashtable
        Dictionary<String, String>
            d = new Hashtable<String, String>();

        // Print the Dictionary
        System.out.println("\nDictionary: " + d);

        // check if this dictionary is empty
        // using isEmpty() method
        if (d.isEmpty()) {
            System.out.println("Dictionary "
                               + "is empty");
        }
        else
            System.out.println("Dictionary "
                               + "is not empty");

        // Insert elements in the hashtable
        d.put("a", "GFG");
        d.put("b", "gfg");

        // Print the Dictionary
        System.out.println("\nDictionary: " + d);

        // check if this dictionary is empty
        // using isEmpty() method
        if (d.isEmpty()) {
            System.out.println("Dictionary "
                               + "is empty");
        }
        else
            System.out.println("Dictionary "
                               + "is not empty");

        // Remove elements in the hashtable
        d.remove("a");
        d.remove("b");

        // Print the Dictionary
        System.out.println("\nDictionary: " + d);

        // check if this dictionary is empty
        // using isEmpty() method
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
Dictionary: {}
Dictionary is empty

Dictionary: {b=gfg, a=GFG}
Dictionary is not empty

Dictionary: {}
Dictionary is empty

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/dictionary . html # isEmpty()](https://docs.oracle.com/javase/7/docs/api/java/util/Dictionary.html#isEmpty())