# Java 中的抽象列表迭代器()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract list-listiterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-listiterator-method-in-java-with-examples/)

**[Java . util . abstract list](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的 **listIterator()** 方法用于返回一个列表迭代器，该列表迭代器包含与抽象列表相同的元素，这些元素以适当且相同的顺序从特定位置或索引号开始，并作为参数传递给该方法。

**语法:**

```
ListIterator new_list 
          = AbstractList.listIterator(int index);
```

**参数:**参数*索引*是一个整型值，它指定了列表迭代器开始操作和返回值的元素的位置。

**返回值:**该方法返回使用列表迭代器创建的列表，从指定的*索引*开始。

下面的程序说明了 AbstractList.listIterator()方法:

**程序 1:**

```
// Java code to illustrate listIterator()

import java.util.*;

public class LinkedListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractList
        AbstractList<String>
            abs_list = new LinkedList<String>();

        // Use add() method to add elements in the list
        abs_list.add("Geeks");
        abs_list.add("for");
        abs_list.add("Geeks");
        abs_list.add("10");
        abs_list.add("20");

        // Displaying the AbstractList
        System.out.println("AbstractList:" + abs_list);

        // Setting the ListIterator at a specified position
        ListIterator list_Iter = abs_list.listIterator(2);

        // Iterating through the created list from the position
        System.out.println("The list is as follows:");

        while (list_Iter.hasNext()) {
            System.out.println(list_Iter.next());
        }
    }
}
```

**Output:**

```
AbstractList:[Geeks, for, Geeks, 10, 20]
The list is as follows:
Geeks
10
20

```

**程序 2:**

```
// Java code to illustrate listIterator()

import java.util.*;

public class LinkedListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractList
        AbstractList<Integer>
            abs_list = new LinkedList<Integer>();

        // Use add() method to add elements in the list
        abs_list.add(10);
        abs_list.add(20);
        abs_list.add(30);
        abs_list.add(40);
        abs_list.add(50);

        // Displaying the AbstractList
        System.out.println("AbstractList:" + abs_list);

        // Setting the ListIterator at a specified position
        ListIterator list_Iter = abs_list.listIterator(2);

        // Iterating through the created list from the position
        System.out.println("The list is as follows:");

        while (list_Iter.hasNext()) {
            System.out.println(list_Iter.next());
        }
    }
}
```

**Output:**

```
AbstractList:[10, 20, 30, 40, 50]
The list is as follows:
30
40
50

```