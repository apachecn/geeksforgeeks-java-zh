# 如何在 Java 中获取 LinkedList 的子列表？

> 原文:[https://www . geeksforgeeks . org/how-get-sub-list of-linked list-in-Java/](https://www.geeksforgeeks.org/how-to-get-sublist-of-linkedlist-in-java/)

[链表](https://www.geeksforgeeks.org/linked-list-in-java/)是 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分。这个类是[链表数据结构](https://www.geeksforgeeks.org/data-structures/linked-list/)的实现，这是一个线性数据结构，其中元素不存储在连续的位置，每个元素都是一个独立的对象，有数据部分和地址部分。

给定 LinkedList 中存在的元素列表，我们需要找到给定范围的子列表的元素。

**示例:**

```java
The elements of the  LinkedList are: [3, 5, 2, 1, 7, 8]

Enter the start and end of the required sublist: 
      start position -> 1
      end position   -> 4
The required SubList is: [5, 2, 1]

where start position is inclusive and the end position is exclusive
```

**方法:使用默认的** [**子列表()**](https://www.geeksforgeeks.org/arraylist-sublist-method-in-java-with-examples/) **方法出现在 util 包的 LinkedList 类中。**

这个很简单，很直接。我们基本上使用**Java . util . linkedlist . sublist()。**

**语法:**

```java
public List subList(int fromIndex, int toIndex)
```

**参数:**该方法将以下参数作为参数。

*   **从索引–**子列表的低端点(含)
*   **到索引–**子列表的高端点(不包括)

**返回值:**该方法返回列表中指定范围的**视图。**

**算法:**

*   在链接列表中输入元素或获取链接列表。
*   输入要查找的子列表的范围的起点(包括 0)。
*   输入范围的结尾(不包括 0)。
*   使用 start 和 end 作为 subList()方法的参数，并将其分配给一个新列表来存储该子列表。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to get Sublist of LinkedList

import java.util.LinkedList;
import java.util.List;

public class subLinkedList {
    public static void main(String[] args)
    {
        LinkedList<String> list = new LinkedList<String>();

        // adding elements
        list.add("apple");
        list.add("mango");
        list.add("peach");
        list.add("guava");
        list.add("banana");
        list.add("lichi");

        // printing initial elements
        System.out.println(
            "The elements of the  LinkedList are: " + list);

        System.out.println(
            "Enter the start and end of the required sublist: ");

        // entering start and end indices
        int start = 2, end = 5;

        List sublist = list.subList(start, end);
        System.out.println("The required SubList is: "
                           + sublist);
    }
}
```

**Output**

```java
The elements of the  LinkedList are: [apple, mango, peach, guava, banana, lichi]
Enter the start and end of the required sublist: 
The required SubList is: [peach, guava, banana]
```

**例 2:从链表的链表中获取子链表。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to get the sublist from
// Linked List of Linked lists

import java.util.LinkedList;
import java.util.List;

public class subLinkedList {
    public static void main(String[] args)
    {
        // creating linkedlist of linkedlists
        LinkedList<LinkedList<Integer> > list
            = new LinkedList<>();

        // creating lists
        LinkedList<Integer> list1 = new LinkedList<>();
        list1.add(8);
        list1.add(0);

        LinkedList<Integer> list2 = new LinkedList<>();
        list2.add(10);
        list2.add(4);
        list2.add(3);
        list2.add(5);

        LinkedList<Integer> list3 = new LinkedList<>();
        list3.add(1);
        list3.add(2);
        list3.add(9);

        // adding linkedlists to main linkedlist
        list.add(list1);
        list.add(list2);
        list.add(list3);

        // printing initial lists
        System.out.println(
            "The elements of the  LinkedList are: " + list);

        System.out.println(
            "Enter the start and end of the required sublists: ");

        // entering start and end indices
        int start = 1, end = 3;

        List sublist = list.subList(start, end);

        System.out.println("The required SubList is: "
                           + sublist);
    }
}
```

**Output**

```java
The elements of the  LinkedList are: [[8, 0], [10, 4, 3, 5], [1, 2, 9]]
Enter the start and end of the required sublists: 
The required SubList is: [[10, 4, 3, 5], [1, 2, 9]]
```