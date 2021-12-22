# Java 中的抽象顺序列表 toString()方法，示例

> 原文:[https://www . geeksforgeeks . org/abstractsequentialist-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-tostring-method-in-java-with-example/)

**Java 抽象顺序列表**的 **toString()** 方法用于返回集合元素的字符串表示。

字符串表示形式包括集合元素的列表表示形式，这些元素按照迭代器选取的顺序排列，并以方括号[]结束。此方法主要用于在字符串表示形式中显示字符串类型以外的集合(例如:对象、整数)。

**语法:**

```
public String toString()
```

**参数**该方法不取任何参数。

**返回**该方法返回集合的**字符串表示**。

以下示例说明了 toString()方法:

**例 1:**

```
// Java program to demonstrate
// Abstract Collection toString() method

import java.util.*;

public class collection {
    public static void main(String args[])
    {
        // Creating an Empty AbstractSequentialList
        AbstractSequentialList<String> abs
            = new LinkedList<String>();

        // Use add() method
        // to add elements to the Collection
        abs.add("Welcome");
        abs.add("To");
        abs.add("Geeks");
        abs.add("For");
        abs.add("Geeks");

        // Using toString() method
        System.out.println(abs.toString());
    }
}
```

**Output:**

```
[Welcome, To, Geeks, For, Geeks]

```

**例 2:**

```
// Java program to demonstrate
// Abstract Collection toString() method

import java.util.*;

public class collection {
    public static void main(String args[])
    {
        // Creating an Empty AbstractSequentialList
        AbstractSequentialList<Integer> abs
            = new LinkedList<Integer>();

        // Use add() method
        // to add elements to the Collection
        abs.add(10);
        abs.add(20);
        abs.add(30);
        abs.add(40);

        // Using toString() method
        System.out.println(abs.toString());
    }
}
```

**Output:**

```
[10, 20, 30, 40]

```