# Java 中的 LinkedList 克隆()方法

> 原文:[https://www . geesforgeks . org/linked list-clone-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-clone-method-in-java/)

Java.util.LinkedList.clone()方法用于创建上述链表的[浅拷贝](https://en.wikipedia.org/wiki/Object_copying#Shallow_copy)。它只是创建了一个列表的副本。

**语法:**

```
LinkedList.clone()
```

**参数:**该方法不取任何参数。

**返回值:**该函数返回链表实例的副本。

下面程序举例说明了 Java.util.LinkedList.clone()方法:

```
// Java code to illustrate clone() method
import java.io.*;
import java.util.LinkedList;

public class LinkedListDemo {

    public static void main(String args[]) {

        // Creating an empty LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // Use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Displaying the list
        System.out.println("First LinkedList:" + list);

        // Creating another linked list and copying
        LinkedList sec_list = new LinkedList();
        sec_list = (LinkedList) list.clone();

        // Displaying the other linked list
        System.out.println("Second LinkedList is:" + sec_list);
    }
}
```

**输出:**

```
First LinkedList:[Geeks, for, Geeks, 10, 20]
Second LinkedList is:[Geeks, for, Geeks, 10, 20]

```