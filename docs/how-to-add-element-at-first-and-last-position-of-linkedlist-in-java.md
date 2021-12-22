# 如何在 Java 中的 LinkedList 首末位置添加元素？

> 原文:[https://www . geesforgeks . org/如何在 java 中添加第一个和最后一个链接位置的元素列表/](https://www.geeksforgeeks.org/how-to-add-element-at-first-and-last-position-of-linkedlist-in-java/)

LinkedList 是存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中的[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分。这个类是 LinkedList 数据结构的一个实现，linked list 数据结构是一个线性数据结构，其中元素不是以连续的方式存储的，每个元素都是一个单独的对象，有一个数据字段和地址字段。现在我们得到了一个链表，任务很简单，就是在链表的第一个和最后一个位置插入元素，这是借助链表类中的方法来实现的，即 [addFirst()](https://www.geeksforgeeks.org/linkedlist-addfirst-method-in-java/) 和 [*addLast()方法*](https://www.geeksforgeeks.org/linkedlist-addlast-method-in-java) 。

插图:

```
Input : LinkedList: ['e', 'e', 'k'], insert at first = 'G', insert at last = 's' 
Output: LinkedList: ['G', 'e', 'e', 'k', 's']  
```

```
Input : LinkedList: [2, 3, 4], insert at first = 1, insert at last = 5 
Output: LinkedList: [1, 2, 3, 4, 5] 
```

如上所述，在借助[链接列表类](https://www.geeksforgeeks.org/linked-list-in-java/)的 addFirst()和 addLast()方法的帮助下，可以实现这一点。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Insert Elements in LinkedList
// at first and last position to showcase
// addFirst() and addlast() Method

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an empty LinkedList of string type
        LinkedList<String> linkedList
            = new LinkedList<String>();

        // Note: By default, elements are inserted at last

        // Adding elements to the linkedList
        // using add() method
        linkedList.add("e");
        linkedList.add("e");
        linkedList.add("k");

        // Printing the elements in current LinkedList
        System.out.println("Linked list: " + linkedList);

        // Customly inserting element at first position
        linkedList.addFirst("G");

        // Inserting at last position
        linkedList.addLast("s");

        // Print the updated LinkedList
        System.out.println("Updated Linked list: "
                           + linkedList);
    }
}
```

**Output:** 

```
Linked list: [e, e, k]
Updated Linked list: [G, e, e, k, s]
```

> **注意:** add()和 addLast()提供相同的功能。LinkedList 实现了两个接口，[德客](https://www.geeksforgeeks.org/deque-interface-java-example/)和[队列](https://www.geeksforgeeks.org/queue-interface-java/)。它从 Deque 继承 add()，从 Queue 继承 addLast()。