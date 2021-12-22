# Java 中的 LinkedList set()方法

> 原文:[https://www . geesforgeks . org/linked list-set-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-set-method-in-java/)

Java.util.LinkedList.set()方法用于将使用 LinkedList 类创建的链表中的任何特定元素替换为另一个元素。这可以通过在 set()方法的参数中指定要替换的元素和新元素的位置来实现。

**语法:**

```
LinkedList.set(int index, Object element)

```

**参数:**该函数接受两个参数，如上语法所示，如下所述。

*   **索引**:这是整型的，指的是链表中要替换的元素的位置。
*   **元素**:是替换现有元素的新元素，与链表对象类型相同。

**返回值:**该方法返回链表中被新值替换的前一个值。

下面的程序说明了 Java.util.LinkedList.set()方法:

```
// Java code to illustrate set()
import java.io.*;
import java.util.LinkedList;

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

        // Using set() method to replace Geeks with GFG
        System.out.println("The Object that is replaced is: " + list.set(2, "GFG"));

        // Using set() method to replace 20 with 50
        System.out.println("The Object that is replaced is: " + list.set(4, "50"));

        // Displaying the modified linkedlist
        System.out.println("The new LinkedList is:" + list);
    }
}
```

**Output:**

```
LinkedList:[Geeks, for, Geeks, 10, 20]
The Object that is replaced is: Geeks
The Object that is replaced is: 20
The new LinkedList is:[Geeks, for, GFG, 10, 50]

```