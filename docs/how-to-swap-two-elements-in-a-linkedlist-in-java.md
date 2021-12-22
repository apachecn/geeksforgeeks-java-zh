# 如何在 Java 中交换链表中的两个元素？

> 原文:[https://www . geesforgeks . org/how-swap-two-elements-in-a-linked list-in-Java/](https://www.geeksforgeeks.org/how-to-swap-two-elements-in-a-linkedlist-in-java/)

给定一个[链表](https://www.geeksforgeeks.org/data-structures/linked-list/)，任务是在不干扰两个元素链接的情况下交换它们。有多种交换方式。通过交换节点内部的元素和交换完整的节点，可以使用交换元素。

**例:**

```java
Input :- 10->11->12->13->14->15
         element1 = 11
         element2 = 14

Output :- 10->14->12->13->11->15
```

**方法 1:使用内置设置方法**

使用[方法交换链表中的两个元素。为了实现我们想要的输出，首先，确保提供给我们的两个元素在链表中都可用。如果两个元素都不存在，只需返回。使用 set()方法将 element1 的位置设置为 element2 的位置，反之亦然。](https://www.geeksforgeeks.org/set-list-java/)

下面是上述方法的代码:

T3】JavaT5

```java
// Swaping two elements in a Linked List in Java

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        LinkedList<Integer> ll = new LinkedList<>();

        // Adding elements to Linked List
        ll.add(10);
        ll.add(11);
        ll.add(12);
        ll.add(13);
        ll.add(14);
        ll.add(15);

        // Elements to swap
        int element1 = 11;
        int element2 = 14;

        System.out.println("Linked List Before Swaping :-");

        for (int i : ll) {
            System.out.print(i + " ");
        }

        // Swapping the elements
        swap(ll, element1, element2);
        System.out.println();
        System.out.println();

        System.out.println("Linked List After Swaping :-");

        for (int i : ll) {
            System.out.print(i + " ");
        }
    }

    // Swap Function
    public static void swap(LinkedList<Integer> list,
                            int ele1, int ele2)
    {

        // Getting the positions of the elements
        int index1 = list.indexOf(ele1);
        int index2 = list.indexOf(ele2);

        // Returning if the element is not present in the
        // LinkedList
        if (index1 == -1 || index2 == -1) {
            return;
        }

        // Swapping the elements
        list.set(index1, ele2);
        list.set(index2, ele1);
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N)，其中 N 为链表的长度

**方法 2:使用我们自己的链表**

给定一个链表，提供两个值，用两个给定的节点交换节点。

下面是上述方法的实现:

T3】JavaT5

```java
// Java Program to Swap Two Elements in a LinkedList
class Node {
    int data;
    Node next;
    Node(int d)
    {
        data = d;
        next = null;
    }
}

class LinkedList {
    Node head; // head of list

    // Function to swap Nodes x and y in
    // linked list by changing links
    public void swapNodes(int x, int y)
    {
        // Nothing to do if x and y are same
        if (x == y)
            return;

        // Search for x (keep track of prevX and CurrX)
        Node prevX = null, currX = head;
        while (currX != null && currX.data != x) {
            prevX = currX;
            currX = currX.next;
        }

        // Search for y (keep track of prevY and currY)
        Node prevY = null, currY = head;
        while (currY != null && currY.data != y) {
            prevY = currY;
            currY = currY.next;
        }

        // If either x or y is not present, nothing to do
        if (currX == null || currY == null)
            return;

        // If x is not head of linked list
        if (prevX != null)
            prevX.next = currY;
        else // make y the new head
            head = currY;

        // If y is not head of linked list
        if (prevY != null)
            prevY.next = currX;
        else // make x the new head
            head = currX;

        // Swap next pointers
        Node temp = currX.next;
        currX.next = currY.next;
        currY.next = temp;
    }

    // Function to add Node at beginning of list.
    public void push(int new_data)
    {
        // 1\. alloc the Node and put the data
        Node new_Node = new Node(new_data);

        // 2\. Make next of new Node as head
        new_Node.next = head;

        // 3\. Move the head to point to new Node
        head = new_Node;
    }

    // This function prints contents of linked
    // list starting from the given Node
    public void printList()
    {
        Node tNode = head;
        while (tNode != null) {
            System.out.print(tNode.data + " ");
            tNode = tNode.next;
        }
        System.out.println();
    }

    // Driver program to test above function
    public static void main(String[] args)
    {
        LinkedList llist = new LinkedList();

        // The constructed linked list is:
        // 1->2->3->4->5->6->7
        llist.push(7);
        llist.push(6);
        llist.push(5);
        llist.push(4);
        llist.push(3);
        llist.push(2);
        llist.push(1);

        System.out.println("Linked List Before Swaping :-");
        llist.printList();

        llist.swapNodes(4, 3);

        System.out.println("Linked List After Swaping :-");
        llist.printList();
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N)，其中 N 为链表的长度