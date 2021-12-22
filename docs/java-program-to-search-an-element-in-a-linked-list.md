# 在链表中搜索元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-search-a-element-in-a-link-list/](https://www.geeksforgeeks.org/java-program-to-search-an-element-in-a-linked-list/)

**先决条件:**[Java 中的链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)

**链接列表**是一种线性数据结构，其中元素不存储在连续的存储位置。每个元素都是一个单独的对象，称为**节点**，包含数据部分和地址部分。使用指针或引用来链接元素。在删除和插入的情况下，链表优于数组，因为它们需要 0(1)个操作时间。

**链表的优势:**

*   And insertion and deletion takes O(1).
*   Dynamics in nature.
*   Memory is discontinuous.

**语法:**

```java
LinkedList<ClassName> variableName = new LinkedList<>();

Example:
LinkedList<Integer> ll = new LinkedList<>();

```

**任务:**

在链接列表中搜索元素。

**进场:**

当链表直接提供给我们时，我们可以使用 for 循环遍历链表并找到元素。在这种情况下，如果不允许我们使用预先构建的库，我们需要创建自己的链表并搜索元素。

**例:**

```java
Input: ll1 = [10, 20, 30, -12, 0, 23, -2, 12] 
       element = 23
Output: 5

Input: ll2 = [1, 2, 3, 4, 5]
       element = 3
Output: 2

```

以下是我们在链表中搜索元素的两种方法。

**方法一:当我们被允许使用内置库**

*   First, initialize a linked list.
*   A for loop is used to traverse the elements in the linked list.

下面是上述方法的实现:

T3】JavaT5

```java
// Java Program to find an element in a Linked List

// Importing the Linked List class
import java.util.LinkedList;

class SearchInALinkedList {
    public static void main(String[] args)
    {
        // Initializing the Linked List
        LinkedList<Integer> ll = new LinkedList<>();

        // Adding elements to the Linked List
        ll.add(1);
        ll.add(2);
        ll.add(3);
        ll.add(4);
        ll.add(5);
        ll.add(6);
        ll.add(7);

        // Element to be searched
        int element = 4;

        // Initializing the answer to the index -1
        int ans = -1;

        // Traversing through the Linked List
        for (int i = 0; i < ll.size(); i++) {

            // Eztracting each element in
            // the Linked List
            int llElement = ll.get(i);

            // Checking if the extracted element is equal to
            // the element to be searched
            if (llElement == element) {

                // Assigning the index of the
                // element to answer
                ans = i;
                break;
            }
        }
        // Checking if the element is present in the Linked
        // List
        if (ans == -1) {
            System.out.println("Element not found");
        }
        else {
            System.out.println(
                "Element found in Linked List at " + ans);
        }
    }
}
```

T6T8**输出**T1

**时间复杂度:**O(n)**n**是链表中存在的元素个数。

**方法二:当我们不允许使用内置库**

*   First, create a generic node class.
*   Create a LinkedList class and initialize the header node to null.
*   Create the required add and search functions.
*   Initialize the linked list in the main method.
*   Use the search method to find elements.

下面是上述方法的实现:

T3】JavaT5

```java
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

    // Points to the head of the Linked
    // List i.e the first element
    Node<E> head = null;
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

    // Searches the Linked List for the given element and
    // returns it's particular index if found else returns
    // -1
    public int search(E element)
    {

        if (head == null) {
            return -1;
        }

        int index = 0;
        Node<E> temp = head;

        // While loop is used to search the entire Linked
        // List starting from the tail
        while (temp != null) {

            // Returns the index of that particular element,
            // if found.
            if (temp.data == element) {
                return index;
            }

            // Gradually increases index while
            // traversing through the Linked List
            index++;
            temp = temp.next;
        }

        // Returns -1 if the element is not found
        return -1;
    }
}

public class GFG {
    public static void main(String[] args) throws Exception
    {

        // Initializing the Linked List
        LinkedList<Integer> ll = new LinkedList<>();

        // Adding elements to the Linked List
        ll.add(1);
        ll.add(10);
        ll.add(12);
        ll.add(-1);
        ll.add(0);
        ll.add(-19);
        ll.add(34);

        // Element to be searched
        int element = -1;

        // Searching the Linked
        // List for the element
        int ans = ll.search(-1);

        if (ans == -1) {
            System.out.println(
                "Element not found in the Linked List");
        }
        else
            System.out.println(
                "Element found in the Linked List at "
                + ans);
    }
}
```

T6T8**输出**T1

**时间复杂度:**O(n)**n**是链表中存在的元素个数。