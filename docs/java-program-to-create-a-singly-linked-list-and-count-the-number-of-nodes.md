# 创建单链表并计算节点数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-create-single-link-list-and-count-nodes-number/](https://www.geeksforgeeks.org/java-program-to-create-a-singly-linked-list-and-count-the-number-of-nodes/)

链表是一种线性数据结构。链表元素不是存储在一个连续的位置，元素是使用指针链接的。单链表是节点的集合，其中每个节点有两个部分，一个是数据，另一个是链接部分。

**示例:**

```
Input : AddNodes = {2, 3, 4}
Output: LinkedList = [2, 3, 4]
        Size = 3

Input : AddNodes = {1, 2, 3, 4, 5}
Output: LinkedList = [1, 2, 3, 4, 5]
        Size = 5
```

**操作:**

1.  创建节点链接列表
2.  定义像添加节点()，显示节点()和计数节点()这样的方法
3.  得到最终答案

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Create a Singly Linked List
// of n Nodes and Count the Number of Nodes
import java.io.*;
import java.util.*;

public class LinkedListCreation {

    class Node {
        int data;
        Node next;

        // constructor to create new node
        Node(int data)
        {
            this.data = data;
            this.next = null;
        }
    }

    // Initially both head and tail are not
    // pointing to any other node
    Node head = null;
    Node tail = null;

    // method to add newNode in Linked List
    void addNode(int data)
    {

        Node newNode = new Node(data);

        // Checks if the list is empty
        if (head == null) {
            // If list is empty, both head and
            // tail will point to new node
            head = newNode;
            tail = newNode;
        }
        else {

            tail.next = newNode;
            // storing newnode in tail
            tail = newNode;
        }
    }
    // display linked list
    void displayNodes()
    {

        Node current = head;
        if (head == null) {
            System.out.println("Empty");
            return;
        }
        System.out.println("Nodes : ");
        while (current != null) {

            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
    }

    // method to count nodes
    int countNodes()
    {
        // Initially zero
        int count = 0;

        Node currentNode = head;
        // iterate until all the nodes are present
        while (currentNode != null) {

            count++;
            currentNode = currentNode.next;
        }
        // return the count
        return count;
    }

    public static void main(String[] args)
    {

        LinkedListCreation L1 = new LinkedListCreation();

        L1.addNode(1);
        L1.addNode(2);
        L1.addNode(3);
        L1.addNode(4);

        // Displays the nodes present in the list
        L1.displayNodes();

        // Counts the nodes present in the given list
        System.out.println("Total Nodes: "
                           + L1.countNodes());
    }
}
```

**Output**

```
Nodes : 
1 2 3 4 
Total Nodes: 4
```

**新节点插入的时间复杂度:**

1.  **起初:** O(1)
2.  **End:**O(N)，其中 N 为链表的大小

**计算节点数的时间复杂度:** O(N)，其中 N 是节点数