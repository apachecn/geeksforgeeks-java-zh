# 用示例

将抽象设置为 Java 中的 Array()方法

> 原文:[https://www . geesforgeks . org/abstract set-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractset-toarray-method-in-java-with-example/)

**Java 抽象集**的 **toArray()** 方法用于形成与抽象集相同元素的数组。基本上，它将抽象集中的所有元素复制到一个新数组中。

**语法:**

```
Object[] arr = AbstractSet.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个包含与抽象集相似元素的数组。

下面的程序说明了 AbstractSet.toArray()方法:

**程序 1:**

```
// Java code to illustrate toArray()

import java.util.*;

public class AbstractSetDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSet
        AbstractSet<String>
            abs_col = new TreeSet<String>();

        // Use add() method to add
        // elements into the AbstractSet
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSet
        System.out.println("The AbstractSet: "
                           + abs_col);

        // Creating the array and using toArray()
        Object[] arr = abs_col.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```
The AbstractSet: [For, Geeks, To, Welcome]
The array is:
For
Geeks
To
Welcome

```

**程序 2:**

```
// Java code to illustrate toArray()

import java.util.*;

public class AbstractSetDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSet
        AbstractSet<Integer>
            abs_col = new TreeSet<Integer>();

        // Use add() method to add
        // elements into the AbstractSet
        abs_col.add(10);
        abs_col.add(15);
        abs_col.add(30);
        abs_col.add(20);
        abs_col.add(5);
        abs_col.add(25);

        // Displaying the AbstractSet
        System.out.println("The AbstractSet: "
                           + abs_col);

        // Creating the array and using toArray()
        Object[] arr = abs_col.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```
The AbstractSet: [5, 10, 15, 20, 25, 30]
The array is:
5
10
15
20
25
30

```