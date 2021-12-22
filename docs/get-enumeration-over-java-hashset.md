# 通过 Java HashSet 获取枚举

> 原文:[https://www . geesforgeks . org/get-enumeration-over-Java-hashset/](https://www.geeksforgeeks.org/get-enumeration-over-java-hashset/)

[HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 类实现了 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)，由 HashMap 实例哈希表支持。对于集合的迭代顺序没有保证，这意味着随着时间的推移，类不能保证元素的顺序不变。此类允许空元素。 [java.util.Collections](https://www.geeksforgeeks.org/collections-in-java-2/) 类枚举方法用于返回指定集合的枚举。

要通过哈希集返回枚举:

**语法:**

```
public static Enumeration enumeration(Collection c)
```

**使用的方法:**[**hasmorelements()**](https://www.geeksforgeeks.org/enumeration-hasmoreelements-method-in-java-with-examples/)**方法。**

**实现枚举接口的对象一次创建一个，即一组对象。hasMoreElements()枚举方法，用于测试此枚举是否包含更多元素。如果枚举包含更多的元素，那么它将返回 true 否则返回 false。**

****语法:****

```
boolean hasMoreElements()
```

****返回值:**如果这个枚举对象中至少有一个要给定的附加元素，这个方法返回 true，否则返回 false。**

**以下是上述方法的全面实施:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Getting Enumeration over Java HashSet
import java.util.*;
import java.util.Enumeration;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of HashSet
        // String type here- name
        HashSet<String> name = new HashSet<>();

        // Adding element to HashSet
        // Custom inputs
        name.add("Nikhil");
        name.add("Akshay");
        name.add("Bina");
        name.add("Chintu");
        name.add("Dhruv");

        // Creating object of type Enumeration<String>
        Enumeration e = Collections.enumeration(name);

        // Condition check using hasMoreElements() method
        while (e.hasMoreElements())

            // print the enumeration
            System.out.println(e.nextElement());
    }
}
```

****Output**

```
Dhruv
Akshay
Chintu
Bina
Nikhil
```** 

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Getting Enumeration over Java HashSet
import java.util.*;
import java.util.Enumeration;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of HashSet
        // String type here- name
        HashSet<String> gfg = new HashSet<>();

        // Adding element to HashSet
        // Custom inputs
        gfg.add("Welcome");
        gfg.add("On");
        gfg.add("GFG");

        // Creating object of type Enumeration<String>
        Enumeration e = Collections.enumeration(gfg);

        // Condition check using hasMoreElements() method
        while (e.hasMoreElements())

            // print the enumeration
            System.out.println(e.nextElement());
    }
}
```

****Output**

```
GFG
Welcome
On
```**