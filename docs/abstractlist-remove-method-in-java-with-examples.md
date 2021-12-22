# 抽象列表移除()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/abstract list-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-remove-method-in-java-with-examples/)

**[Java . util . abstract list](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的 **remove(int index)** 方法用于从特定位置或索引从抽象列表中移除元素。

**语法:**

```
AbstractList.remove(int index)
```

**参数:**参数*索引*是整数数据类型，指定要从抽象列表中删除的元素的位置。

**返回值:**该方法返回刚从列表中删除的元素。

下面的程序说明了 AbstractList.remove(int index)方法:

**程序 1:**

```
// Java code to illustrate remove() method

import java.util.*;
import java.util.LinkedList;

public class AbstractListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractList
        AbstractList<String>
            list = new LinkedList<String>();

        // Using add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Output the list
        System.out.println("AbstractList: " + list);

        // Remove the head using remove()
        list.remove(3);

        // Print the final list
        System.out.println("Final AbstractList: " + list);
    }
}
```

**Output:**

```
AbstractList: [Geeks, for, Geeks, 10, 20]
Final AbstractList: [Geeks, for, Geeks, 20]

```

**程序 2:**

```
// Java code to illustrate remove() when position of
// element is passed as parameter

import java.util.*;
import java.util.LinkedList;

public class AbstractListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractList
        AbstractList<String> list = new LinkedList<String>();

        // Use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Output the list
        System.out.println("AbstractList:" + list);

        // Remove the head using remove()
        list.remove(0);

        // Print the final list
        System.out.println("Final AbstractList:" + list);
    }
}
```

**Output:**

```
AbstractList:[Geeks, for, Geeks, 10, 20]
Final AbstractList:[for, Geeks, 10, 20]

```