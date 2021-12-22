# 用示例

在 Java 中设置 toArray()方法

> 原文:[https://www . geesforgeks . org/hashset-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/hashset-toarray-method-in-java-with-example/)

**Java HashSet** 的 **toArray()** 方法用于形成一个数组，数组中的元素与 HashSet 中的元素相同。基本上，它将 HashSet 中的所有元素复制到一个新数组中。

**语法:**

```java
Object[] arr = HashSet.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个数组，该数组包含与 HashSet 类似的元素。

下面的程序说明了 HashSet.toArray()方法:

**程序 1:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class HashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty HashSet
        HashSet<String>
            abs_col = new HashSet<String>();

        // Use add() method to add
        // elements into the HashSet
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the HashSet
        System.out.println("The HashSet: "
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

```java
The HashSet: [Geeks, For, Welcome, To]
The array is:
Geeks
For
Welcome
To

```

**程序 2:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class HashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty HashSet
        HashSet<Integer>
            abs_col = new HashSet<Integer>();

        // Use add() method to add
        // elements into the HashSet
        abs_col.add(10);
        abs_col.add(15);
        abs_col.add(30);
        abs_col.add(20);
        abs_col.add(5);
        abs_col.add(25);

        // Displaying the HashSet
        System.out.println("The HashSet: "
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

```java
The HashSet: [20, 5, 25, 10, 30, 15]
The array is:
20
5
25
10
30
15

```