# Java 中抽象顺序列表到数组()方法，示例

> 原文:[https://www . geesforgeks . org/abstractsequentialilist-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-toarray-method-in-java-with-example/)

**Java 抽象顺序列表**的 **toArray()** 方法用于形成与抽象顺序列表相同元素的数组。基本上，它将抽象序列列表中的所有元素复制到一个新数组中。

**语法:**

```java
Object[] arr = AbstractSequentialList.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个包含类似于抽象序列列表元素的数组。

下面的程序说明了 abstractsequentialilist . to array()方法:

**程序 1:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String>
            abs_col = new LinkedList<String>();

        // Use add() method to add
        // elements into the AbstractSequentialList
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSequentialList
        System.out.println("The AbstractSequentialList: "
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
The AbstractSequentialList: [Welcome, To, Geeks, For, Geeks]
The array is:
Welcome
To
Geeks
For
Geeks

```

**程序 2:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSequentialList
        AbstractSequentialList<Integer>
            abs_col = new LinkedList<Integer>();

        // Use add() method to add
        // elements into the AbstractSequentialList
        abs_col.add(10);
        abs_col.add(15);
        abs_col.add(30);
        abs_col.add(20);
        abs_col.add(5);
        abs_col.add(25);

        // Displaying the AbstractSequentialList
        System.out.println("The AbstractSequentialList: "
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
The AbstractSequentialList: [10, 15, 30, 20, 5, 25]
The array is:
10
15
30
20
5
25

```