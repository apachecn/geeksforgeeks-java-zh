# Java 中的 LinkedList addLast()方法

> 原文:[https://www . geesforgeks . org/linked list-addlast-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-addlast-method-in-java/)

java 中的 java.util.LinkedList.addLast()方法用于在 LinkedList 的末尾插入特定的元素。
**语法:**

```java
void addLast(Object element)
```

**参数:**该函数接受单个参数*元素*，如上语法所示。由该参数指定的元素被附加在列表的末尾。
**返回值:**此方法不返回值。
下面的程序说明了 Java.util.LinkedList.addLast()方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate boolean addLast()
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

      // Displaying the current list
      System.out.println("The list is:" + list);

      // Adding new elements at the end of list using addLast()
      list.addLast("At");
      list.addLast("Last");

      // Displaying the new list
      System.out.println("The new List is:" + list);
   }
}
```

输出:

```java
The list is:[Geeks, for, Geeks, 10, 20]
The new List is:[Geeks, for, Geeks, 10, 20, At, Last]
```