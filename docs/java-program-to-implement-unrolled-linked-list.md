# 实现展开链表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-展开-链表/](https://www.geeksforgeeks.org/java-program-to-implement-unrolled-linked-list/)

展开的链接列表是一种特殊类型的链接列表，其中每个节点存储一个元素数组，这与简单的链接列表不同。这里我们使用一个数组列表和一个构造函数来初始化展开链表的大小。元素被添加到第一个节点，直到它被填充，然后创建一个具有相同大小的新节点。

节点类有两种方法，即

1.  建造者
2.  一种以整数为参数的插入方法。

**实施:**

*   向展开的链表添加元素
*   从展开的链表中删除元素

**示例 1:** 向展开的链表添加元素

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to implement Unrolled Linked List

// Importing all input output classes
import java.io.*;
// Importing all utility classes from
// java.util package
import java.util.*;

// Class 1
// Main class
class GFG {

    // Nested static class
    static class Node {

        // Member variables of static nested class
        int size;
        ArrayList<Integer> array;

        // Initializing next as NULL
        Node next = null;

        // Method 1
        // Of nested static class
        // To compute over size
        Node(int size)
        {
            // This keyword refers to current object itself
            this.size = size;

            // Storing ArrayList in an array
            array = new ArrayList<>();
        }

        // Method 2
        // To insert element in ana array
        void insert(int n)
        {
            // If array is having empty spaces
            if (array.size() < size) {

                // Add element from List to array
                array.add(n);
            }

            // If array is already full
            else {

                // Array size is zero
                if (next == null) {

                    // Create a new Node and start inserting
                    // elements
                    next = new Node(size);
                    next.insert(n);
                }

                // If array is defined
                else {

                    // Directly start inserting elements
                    next.insert(n);
                }
            }
        }
    }

    // Main driver method
    public static void main(String args[])
    {

        // Creating an object of nested static class
        // inside the main() method

        // Maximum N elements will be printed in a row
        // N is passed as an parameter to the Node
        // N = 3 for illustration, do change and
        // observe how the output varies
        Node x = new Node(3);

        // Adding custom input elements
        // using the insert() method
        x.insert(10);
        x.insert(20);
        x.insert(30);
        x.insert(40);
        x.insert(50);
        x.insert(60);
        x.insert(70);

        // System.out.println(x.array);
        // System.out.println(x.next.array);
        // System.out.println(x.next.next.array);

        // If condition holds true
        // If there are elements left to be inserted
        while (x != null) {

            // Print and display the elements
            System.out.println(x.array);

            // Moving to next element
            x = x.next;
        }
    }
}
```

**Output**

```
[10, 20, 30]
[40, 50, 60]
[70]
```

**示例 2:** 从展开的链表中删除元素

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to implement Unrolled Linked List

// Importing all input output classes
import java.io.*;
// Importing all utility classes from
// java.util package
import java.util.*;

// Class 1
// Main class
class GFG {

    // Nested static class
    static class Node {

        // Member variables of nested class
        int size;
        ArrayList<Integer> array;

        // Initially next is pointing to head
        Node next = null;

        // Constructor of static nested class
        Node(int size)
        {
            // This keyword refers to current object itself
            this.size = size;
            // Assigning current List element
            // to an array
            array = new ArrayList<>();
        }

        // Method 1
        // Of static nested class
        void insert(int n)
        {
            // If there is space in an array
            if (array.size() < size) {

                // Add elements to an array
                array.add(n);
            }

            // Condition check over array
            else {

                // If no array exists, it means
                // head is still pointing to NULL
                if (next == null) {

                    // Create a new node
                    next = new Node(size);

                    // Now, start inserting elements
                    next.insert(n);
                }

                // If next is NOT-NULL
                else {

                    // Start filling array directly
                    next.insert(n);
                }
            }
        }

        // Method 2
        // Of static nested class
        boolean delete(int n)
        {
            if (array.contains(n)) {
                array.remove(array.indexOf(n));
                return true;
            }
            else {
                if (next == null) {
                    return false;
                }
                else {
                    next.delete(n);
                }
                return true;
            }
        }
    }

    // Mai driver method
    public static void main(String args[])
    {

        // Creating an object of Nodetype where
        // 3 as an argument represents maximum elements
        // to be displayed in aa row
        Node x = new Node(3);

        // Adding elements to the above object
        // Custom input entries
        x.insert(10);
        x.insert(20);
        x.insert(30);
        x.insert(40);
        x.insert(50);
        x.insert(60);
        x.insert(70);

        // System.out.println(x.array);
        // System.out.println(x.next.array);
        // System.out.println(x.next.next.array);

        // Display message
        System.out.println(
            "After Inserting all elements : ");

        // Creating an object of static nested class
        Node temp = x;

        while (temp != null) {
            System.out.println(temp.array);
            temp = temp.next;
        }

        // Display message
        System.out.println("Deleting 50 :");

        // Deleting a random element from above added
        // Say it be 50
        x.delete(50);

        // Using the temp variable so that
        // value is not lost
        temp = x;

        // Condition check
        // If temp vaible is NOT-NULL
        while (temp != null) {

            // Print and display the temp array
            // be it oe element or many
            System.out.println(temp.array);

            // Moving to the next node using
            // standard way 'next' in linkedList
            temp = temp.next;
        }
    }
}
```

**Output**

```
After Inserting all elements : 
[10, 20, 30]
[40, 50, 60]
[70]
Deleting 50 :
[10, 20, 30]
[40, 60]
[70]
```