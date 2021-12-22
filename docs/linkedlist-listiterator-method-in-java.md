# Java 中的 LinkedList listIterator()方法

> 原文:[https://www . geeksforgeeks . org/linked list-listiterator-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-listiterator-method-in-java/)

Java . util . LinkedList . listiterator()方法用于返回一个列表迭代器，该列表迭代器包含与 linked list 相同的元素，这些元素以正确且相同的顺序从特定位置或索引号开始，并作为参数传递给该方法。

**语法:**

```
ListIterator *new_list* = LinkedList.listIterator(int index);

```

**参数:**参数*索引*是一个整型值，它指定了列表迭代器开始操作和返回值的元素的位置。

**返回值:**该方法返回使用列表迭代器创建的列表，从指定的*索引*开始。

下面的程序说明了 Java . util . linkedlist . listiterator()方法:

```
// Java code to illustrate listIterator()
import java.io.*;
import java.util.LinkedList;
import java.util.ListIterator;

public class LinkedListDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // Use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Displaying the linkedlist
        System.out.println("LinkedList:" + list);

        // Setting the ListIterator at a specified position
        ListIterator list_Iter = list.listIterator(2);

        // Iterating through the created list from the position
        System.out.println("The list is as follows:");
        while(list_Iter.hasNext()){
           System.out.println(list_Iter.next());
        }
    }
}
```

**输出:**

```
LinkedList:[Geeks, for, Geeks, 10, 20]
The list is as follows:
Geeks
10
20

```