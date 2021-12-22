# 使用递归将给定的数字加到存储在链表中的数字上

> 原文:[https://www . geesforgeks . org/add-给定数字到数字-存储在链表中-使用递归/](https://www.geeksforgeeks.org/add-the-given-digit-to-a-number-stored-in-a-linked-list-using-recursion/)

给定一个代表整数的链表，其中每个节点是所代表整数的一个数字。任务是给所表示的整数加上一个给定的数字 **N** 。
**例:**

> **输入:**【ll = 9】>【9】>【3】>null，N = 7
> **输出:**>【0】>【0】>【0】>null】

**方法:**已经讨论了解决这个问题的迭代方法[这里](https://www.geeksforgeeks.org/add-the-given-digit-to-a-number-stored-in-a-linked-list/)。在本文中，将讨论递归方法。
想法是递归遍历链表，直到到达最后一个节点。到达最后一个节点后，将 **N** 的值添加到其中。添加后，如果该值大于 9，则保持进位和设置模式(数字% 10)值到节点值，并将进位添加到前一个堆栈帧节点，并继续，直到所有堆栈帧从堆栈中清除。
如果在所有堆栈帧被清除后有一个进位，那么用这个值创建一个新节点，它将是指向前一个头的链表的新头。
以下是上述方法的实施:

## C++

```java
// C++ implementation of the approach
#include<bits/stdc++.h>
using namespace std;

// Node class contains value
// and next node reference
struct ListNode
{
    int value;
    ListNode* next;
};

// To store the carry
int carry = 0;
void addNewValue(ListNode*, int);

// Function that calls the recursive method
// addNewValue to add a digit to the
// number represented as the linked list
ListNode* addValue(ListNode* head,
                   int addValue)
{

  // Add the digit recursively
  addNewValue(head, addValue);

  // If there is a carry after the addition
  if (carry != 0)
  {

    // Create a new node
    ListNode* newHead = new ListNode();

    // Assign it with carry
    newHead->value = carry;

    // Make it point to the head of
    // the linked list
    newHead->next = head;
    carry = 0;

    // Make it the new head
    return newHead;
  }

  // If there's not carry then
  // return the previous head
  else
  {
    return head;
  }
}

// Recursive function to add a digit to the number
// represented as the given linked list
void addNewValue(ListNode* head,
                 int addValue)
{

  // If it is the last node in the list
  if (head->next == NULL)
  {

    // Add the digit
    int val = head->value + addValue;

    // Find the carry if any
    head->value = val % 10;
    carry = val / 10;
  }
  else
  {

    // Preserve the current node's value and call
    // the recursive function for the next node
    int val = head->value;
    addNewValue(head->next, addValue);
    val = val + carry;
    head->value = val % 10;
    carry = val / 10;
  }
}

// Utility function to print the linked list
void printList(ListNode* node)
{
  while (node != NULL)
  {
    cout << node->value << " -> ";
    node = node->next;
  }
  cout<<"NULL";
}

// Driver code
int main()
{

  // Create the linked list 9 -> 9 -> 3 -> NULL
  ListNode* head = new ListNode();
  head->value = 9;
  head->next = new ListNode();
  head->next->value = 9;
  head->next->next = new ListNode();
  head->next->next->value = 3;
  head->next->next->next = NULL;

  // Digit to be added
  int n = 7;
  head = addValue(head, n);

  printList(head);
}

// This code is contributed by rutvik_56
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java implementation of the approach

// Node class contains value
// and next node reference
class ListNode {
    int value;
    ListNode next;
}

class GFG {

    // To store the carry
    private static int carry = 0;

    // Function that calls the recursive method
    // addNewValue to add a digit to the
    // number represented as the linked list
    public static ListNode addValue(ListNode head, int addValue)
    {

        // Add the digit recursively
        addNewValue(head, addValue);

        // If there is a carry after the addition
        if (carry != 0) {

            // Create a new node
            ListNode newHead = new ListNode();

            // Assign it with carry
            newHead.value = carry;

            // Make it point to the head of
            // the linked list
            newHead.next = head;
            carry = 0;

            // Make it the new head
            return newHead;
        }

        // If there's not carry then
        // return the previous head
        else {
            return head;
        }
    }

    // Recursive function to add a digit to the number
    // represented as the given linked list
    private static void addNewValue(ListNode head, int addValue)
    {

        // If it is the last node in the list
        if (head.next == null) {

            // Add the digit
            int val = head.value + addValue;

            // Find the carry if any
            head.value = val % 10;
            carry = val / 10;
        }
        else {

            // Preserve the current node's value and call
            // the recursive function for the next node
            int val = head.value;
            addNewValue(head.next, addValue);
            val = val + carry;
            head.value = val % 10;
            carry = val / 10;
        }
    }

    // Utility function to print the linked list
    private static void printList(ListNode node)
    {
        while (node != null) {
            System.out.print(node.value + " -> ");
            node = node.next;
        }
        System.out.print("NULL");
    }

    // Driver code
    public static void main(String[] args)
    {

        // Create the linked list 9 -> 9 -> 3 -> NULL
        ListNode head = new ListNode();
        head.value = 9;
        head.next = new ListNode();
        head.next.value = 9;
        head.next.next = new ListNode();
        head.next.next.value = 3;
        head.next.next.next = null;

        // Digit to be added
        int n = 7;
        head = addValue(head, n);

        printList(head);
    }
}
```

## 计算机编程语言

```java
# Python implementation of the approach

# Node class contains value
# and next node reference
class ListNode:
    def __init__(self, new_data):
        self.value = new_data
        self.next = None

# To store the carry
carry = 0

# Function that calls the recursive method
# addNewValue to add a digit to the
# number represented as the linked list
def addValue(head, addValue):

    global carry

    # Add the digit recursively
    addNewValue(head, addValue)

    # If there is a carry after the addition
    if (carry != 0) :

        # Create a node
        newHead = ListNode(0)

        # Assign it with carry
        newHead.value = carry

        # Make it point to the head of
        # the linked list
        newHead.next = head
        carry = 0

        # Make it the head
        return newHead

    # If there's not carry then
    # return the previous head
    else :
        return head

# Recursive function to add a digit to the number
# represented as the given linked list
def addNewValue(head,addValue):

    global carry

    # If it is the last node in the list
    if (head.next == None) :

        # Add the digit
        val = head.value + addValue

        # Find the carry if any
        head.value = val % 10
        carry = int(val / 10)

    else :

        # Preserve the current node's value and call
        # the recursive function for the next node
        val = head.value
        addNewValue(head.next, addValue)
        val = val + carry
        head.value = val % 10
        carry = int(val / 10)

# Utility function to print the linked list
def printList(node):

    while (node != None) :
        print(node.value ,end= " -> ")
        node = node.next

    print("None")

# Driver code

# Create the linked list 9 -> 9 -> 3 -> None
head = ListNode(0)
head.value = 9
head.next = ListNode(0)
head.next.value = 9
head.next.next = ListNode(0)
head.next.next.value = 3
head.next.next.next = None

# Digit to be added
n = 7
head = addValue(head, n)

printList(head)

# This code is contributed by Arnab Kundu
```

## C#

```java
// C# implementation of the approach
using System;

// Node class contains value
// and next node reference
public class ListNode
{
    public int value;
    public ListNode next;
}

class GFG
{

    // To store the carry
    private static int carry = 0;

    // Function that calls the recursive method
    // addNewValue to add a digit to the
    // number represented as the linked list
    public static ListNode addValue(ListNode head,
                                     int addValue)
    {

        // Add the digit recursively
        addNewValue(head, addValue);

        // If there is a carry after the addition
        if (carry != 0)
        {

            // Create a new node
            ListNode newHead = new ListNode();

            // Assign it with carry
            newHead.value = carry;

            // Make it point to the head of
            // the linked list
            newHead.next = head;
            carry = 0;

            // Make it the new head
            return newHead;
        }

        // If there's not carry then
        // return the previous head
        else
        {
            return head;
        }
    }

    // Recursive function to add a digit to the number
    // represented as the given linked list
    private static void addNewValue(ListNode head,
                                     int addValue)
    {

        // If it is the last node in the list
        if (head.next == null)
        {

            // Add the digit
            int val = head.value + addValue;

            // Find the carry if any
            head.value = val % 10;
            carry = val / 10;
        }
        else
        {

            // Preserve the current node's value and call
            // the recursive function for the next node
            int val = head.value;
            addNewValue(head.next, addValue);
            val = val + carry;
            head.value = val % 10;
            carry = val / 10;
        }
    }

    // Utility function to print the linked list
    private static void printList(ListNode node)
    {
        while (node != null)
        {
            Console.Write(node.value + " -> ");
            node = node.next;
        }
        Console.Write("NULL");
    }

    // Driver code
    public static void Main(String[] args)
    {

        // Create the linked list 9 -> 9 -> 3 -> NULL
        ListNode head = new ListNode();
        head.value = 9;
        head.next = new ListNode();
        head.next.value = 9;
        head.next.next = new ListNode();
        head.next.next.value = 3;
        head.next.next.next = null;

        // Digit to be added
        int n = 7;
        head = addValue(head, n);

        printList(head);
    }
}

// This code is contributed by PrinciRaj1992
```

## java 描述语言

```java
<script>

// JavaScript implementation of the approach

// Node class contains value
// and next node reference
class ListNode {
        constructor() {
                this.value = 0;
                this.next = null;
             }
        }

// To store the carry
let carry = 0;

// Function that calls the recursive method
// addNewValue to add a digit to the
// number represented as the linked list
function addValue( head, addValue)
{

    // Add the digit recursively
    addNewValue(head, addValue);

    // If there is a carry after the addition
    if (carry != 0) {

        // Create a new node
        var newHead = new ListNode();

        // Assign it with carry
        newHead.value = carry;

        // Make it point to the head of
        // the linked list
        newHead.next = head;
        carry = 0;

        // Make it the new head
        return newHead;
        }

    // If there's not carry then
    // return the previous head
    else {
        return head;
    }
}

// Recursive function to add a digit to the number
// represented as the given linked list
function addNewValue( head, addValue)
{

    // If it is the last node in the list
    if (head.next == null) {

        // Add the digit
        let val = head.value + addValue;

        // Find the carry if any
        head.value = val % 10;
        carry = Math.floor(val / 10);
    }
    else {

        // Preserve the current node's value and call
        // the recursive function for the next node
        let val = head.value;
        addNewValue(head.next, addValue);
        val = val + carry;
        head.value = val % 10;
        carry = Math.floor(val / 10);
        }
    }

// Utility function to print the linked list
function printList( node)
{
    while (node != null) {
        document.write(node.value + " -> ");
        node = node.next;
    }
    document.write("NULL");
}

// Driver Code

// Create the linked list 9 -> 9 -> 3 -> NULL
var head = new ListNode();
head.value = 9;
head.next = new ListNode();
head.next.value = 9;
head.next.next = new ListNode();
head.next.next.value = 3;
head.next.next.next = null;

// Digit to be added
let n = 7;
head = addValue(head, n);

printList(head);

</script>
```

**Output:** 

```java
1 -> 0 -> 0 -> 0 -> NULL
```