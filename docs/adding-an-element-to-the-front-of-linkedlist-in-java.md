# 在 Java 中的链表前面添加一个元素

> 原文:[https://www . geeksforgeeks . org/向 java 中的链接列表前端添加元素/](https://www.geeksforgeeks.org/adding-an-element-to-the-front-of-linkedlist-in-java/)

一个[链表](https://www.geeksforgeeks.org/data-structures/linked-list/)是一个线性数据结构，其中的元素不存储在连续的内存位置。这些元素使用指针和地址进行链接。每个元素都被称为一个节点。本文展示了如何在 Java 中的[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)的前面添加一个元素。

**方法 1:(使用自定义方法)**

*   Allocate memory to the new node.
*   Put the element to be inserted into the assigned node.
*   Take the next one of the new nodes as the head.
*   Move the head to the new node.

**例:**

## 爪哇

```java
// Java program to Add an Element
// to the Front of LinkedList

import java.io.*;

class LinkedList {

      // head reference
    Node head;

      // Node class
    class Node {
        int data;
        Node next;

        Node(int d)
        {
            data = d;
            next = null;
        }
    }

    // Inserting node at the front
    public void insertfront(int data)
    {
        // Allocating and inserting the data in that node
        Node new_node = new Node(data);

        // Make the next of the newly allocated node to be
        // the head
        new_node.next = head;

        // Now make the head to be the newly allocated node
        head = new_node;
    }

    // Printing the List
    public void print()
    {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
    }

    public static void main(String args[])
    {
          // create a linkedlist
        LinkedList l = new LinkedList();

          // insert elements at the front
        l.insertfront(6);
        l.insertfront(5);
        l.insertfront(8);
        l.insertfront(9);

          // print the linkedlist
        l.print();
    }
}
```

**输出**

```java
9 8 5 6
```