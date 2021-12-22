# Java 中的 LinkedList get()方法

> 原文:[https://www . geesforgeks . org/linked list-get-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-get-method-in-java/)

Java.util.LinkedList.get()方法用于从 LinkedList 中获取或检索特定索引处的元素。

**语法:**

```java
LinkedList.get(int index)
```

**参数:**参数*索引*是整数数据类型，指定要从链接列表中提取的元素的位置或索引。

**返回值:**该方法返回出现在参数*索引*指定位置的元素。

下面程序举例说明了 Java.util.LinkedList.get()方法:

```java
// Java code to illustrate get() method
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
      System.out.println("LinkedList:" + list);

      // Fetching the specific element from the list
      System.out.println("The element is: " + list.get(2));

   }
}
```

**输出:**

```java
LinkedList:[Geeks, for, Geeks, 10, 20]
The element is: Geeks

```