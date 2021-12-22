# 获取链表第一个和最后一个元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-first-and-last-element-of-a-link-list/](https://www.geeksforgeeks.org/java-program-to-get-the-first-and-the-last-element-of-a-linked-list/)

A [链表](https://www.geeksforgeeks.org/data-structures/linked-list/) 是一种线性数据结构，其中元素不存储在连续的存储位置。给定的任务是检索给定链表的第一个和最后一个元素。

**链表的属性:**

*   Elements are stored in a discontinuous manner.
*   Each element is an object that contains a pointer to the next element.

```
Input: [2, 5, 5, 7, 10, 6]

Output: First element is : 2
        Last element is : 6

Input: [1]

Output: First element is : 1
        Last element is : 1
```

**方法 1:使用内置库**

使用 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中预先构建的[链接表](https://www.geeksforgeeks.org/linked-list-in-java/)类构建一个链接表，并使用预先定义的方法获取相应的值。

**示例:**下面是上述方法的实现:

T5】JavaT7

```
// Java Program to get the first and the last element of a
// Linked List

// Importing the Linked List class from the util package
import java.util.LinkedList;

class AccessFirstAndLastElements {
    public static void main(String[] args)
    {
        // Initializing the Linked List
        LinkedList<Integer> ll = new LinkedList<>();

        // Adding elements to the Linked List
        ll.add(2);
        ll.add(5);
        ll.add(5);
        ll.add(7);
        ll.add(10);
        ll.add(6);

        // Getting the first element
        System.out.println("First Element is : "
                           + ll.getFirst());

        // Getting the last element
        System.out.println("Last Element is : "
                           + ll.getLast());
    }
}
```

T8T10**输出**T1

**时间复杂度:** [getFirst()](https://www.geeksforgeeks.org/linkedlist-getfirst-method-in-java/#:~:text=util.-,LinkedList.,the%20head%20of%20the%20List.&text=Parameters%3A%20This%20method%20does%20not,the%20head%20of%20the%20list.) 取 O(1)时间， [getLast()](https://www.geeksforgeeks.org/linkedlist-getlast-method-in-java/) 取 O(n)，其中 **n** 为链表中的元素个数。

**方法 2:不使用内置方法**

*   Create a generic node class.
*   Create our own linked list class using node class.
*   Create the required add (), getFirst () and getLast () methods.
*   Initialize the linked list.
*   Use the respective get methods to get values.

**示例:**下面是上述方法的实现:

T5】JavaT7

```
// Java program to get the first and last element from a
// Linked List

// A Generic Node class is used to create a Linked List
class Node<E> {

    // Data Stored in each Node of the Linked List
    E data;

    // Pointer to the next node in the Linked List
    Node<E> next;

    // Node class constructor used to initializes the data
    // in each Node
    Node(E data) { this.data = data; }
}

class LinkedList<E> {

    // Points to the head of the Linked List
    // i.e the first element
    Node<E> head;
    int size = 0;

    // Addition of elements to the tail of the Linked List
    public void add(E element)
    {

        // Checks whether the head is created else creates a
        // new one
        if (head == null) {
            head = new Node<>(element);
            size++;
            return;
        }

        // The Node which needs to be added at
        // the tail of the Linked List
        Node<E> add = new Node<>(element);

        // Storing the instance of the
        // head pointer
        Node<E> temp = head;

        // The while loop takes us to the tail of the Linked
        // List
        while (temp.next != null) {

            temp = temp.next;
        }

        // New Node is added at the tail of
        // the Linked List
        temp.next = add;

        // Size of the Linked List is incremented as
        // the elements are added
        size++;
    }

    // Retrieves the first element of the Linked List
    public E getFirst() throws Exception
    {

        // Throws an Exception if the List is empty
        if (head == null) {
            throw new Exception(
                "No elements found in Linked List");
        }

        // Returns the first element
        return head.data;
    }

    // Retrieves the last element of the Linked List
    public E getLast() throws Exception
    {
        // Throws an Exception if the List is empty
        if (head == null) {
            throw new Exception(
                "No elements found in Linked List");
        }

        Node<E> temp = head;

        // The while loop takes us to the tail of the Linked
        // List
        while (temp.next != null) {
            temp = temp.next;
        }

        // Returns the last element
        return temp.data;
    }
}

class AccessFirstAndLastElements {
    public static void main(String[] args) throws Exception
    {
        // Initializing the Linked List
        LinkedList<Integer> ll = new LinkedList<>();

        // Adding elements to the Linked List
        ll.add(2);
        ll.add(5);
        ll.add(5);
        ll.add(7);
        ll.add(10);
        ll.add(6);

        // Getting the first element
        System.out.println("First Element is : "
                           + ll.getFirst());

        // Getting the last element
        System.out.println("Last Element is : "
                           + ll.getLast());
    }
}
```

T8T10**输出**T1

**时间复杂度:getFirst()** 取 O(1)时间， **getLast()** 取 O(n)，其中 **n** 为链表中的元素个数。