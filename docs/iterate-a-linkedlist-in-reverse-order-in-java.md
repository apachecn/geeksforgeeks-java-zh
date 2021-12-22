# 在 Java 中以相反的顺序迭代链表

> 原文:[https://www . geesforgeks . org/iterate-a-linked list-in-reverse-order-in-Java/](https://www.geeksforgeeks.org/iterate-a-linkedlist-in-reverse-order-in-java/)

为了以相反的顺序遍历链表，我们可以使用**降序迭代器**或**列表迭代器**

**1。递减迭代器**

**语法:**

```java
LinkedList<String> linkedlist = new LinkedList<>();

Iterator<String> listIterator = linkedlist.descendingIterator();
```

**返回:**降序迭代器返回指向链表末尾的迭代器。

**2。** **列表迭代器**

**语法:**

```java
LinkedList<String> linkedlist = new LinkedList<>();

ListIterator<String> listIerator = linkedlist.listIterator(linkedlist.size());
```

**参数:**链表的大小，这会使迭代器指向链表的末尾。

**示例 1:使用降序迭代器**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Iterate a LinkedList in Reverse Order
// using descending Iterator

import java.util.Iterator;
import java.util.LinkedList;

public class GFG {
    public static void main(String[] args)
    {
        LinkedList<String> linkedList = new LinkedList<>();

        // adding elements to linked list
        linkedList.add("Geeks");
        linkedList.add("For");
        linkedList.add("Geek");
        linkedList.add("2020");
        linkedList.add("2021");

        // getting an iterator which points at the
        // end of the linkedlist
        Iterator<String> iterator = linkedList.descendingIterator();

        // traversing the linkedlist
        // hasNext() will tell if previous element is
        // available or not
        // next() with descending iterator will return the
        // previous element
        // and after getting the previous element
        // is moves the cursor to next previous element.
        while (iterator.hasNext()) 
        {
            System.out.println(iterator.next());
        }
    }
}
```

**Output**

```java
2021
2020
Geek
For
Geeks

```

**示例 2:使用列表迭代器**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Iterate a LinkedList in Reverse Order
// using List Iterator

import java.util.LinkedList;
import java.util.ListIterator;

public class GFG {
    public static void main(String[] args)
    {

        LinkedList<String> linkedList = new LinkedList<>();

        // adding elements of to the linkedlist
        linkedList.add("Geeks");
        linkedList.add("For");
        linkedList.add("Geek");
        linkedList.add("2020");
        linkedList.add("2021");

        // getting an iterator that points at the end of the
        // linkedlist
        ListIterator<String> listIterator = linkedList.listIterator(linkedList.size());

        // Traversing the linked list
        // hasPrevious() function to check if previous
        // element is present or not previous() function to
        // get the previous element and after getting
        // previous elements it move the cursor to the next
        // previous element
        while (listIterator.hasPrevious())
        {
            System.out.println(listIterator.previous());
        }
    }
}
```

**Output**

```java
2021
2020
Geek
For
Geeks

```