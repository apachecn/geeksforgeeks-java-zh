# Java 中的数组列表与链接列表

> 哎哎哎:# t0]https://www . geeksforgeeks . org/ArrayList-vs-linked list-Java/

[数组](https://www.geeksforgeeks.org/array-data-structure/)是存储在连续存储位置的项目的集合。想法是将多个相同类型的项目存储在一起。但是，数组的限制是数组的大小是预先定义的并且是固定的。解决这个问题有多种方法。本文讨论了为解决这个问题而实现的两个[类](https://www.geeksforgeeks.org/classes-objects-java/)之间的区别，这两个类名为 [**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 和 [**链表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

![](img/31b0e27f7605fef98b55045c08b0df6c.png)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)是 [**集合框架**](https://www.geeksforgeeks.org/collections-in-java-2/) 的一部分。它存在于 [**java.util**](https://www.geeksforgeeks.org/java-util-package-java/) 包中，用 java 为我们提供动态数组。尽管它可能比标准数组慢，但在需要对数组进行大量操作的程序中会很有帮助。我们可以动态添加和删除项目。它会自动调整大小。下面是一个演示数组列表实现的例子。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate Working of an ArrayList

// Importing required classes
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an ArrayList of Integer type
        ArrayList<Integer> arrli
            = new ArrayList<Integer>();

        // Appending the new elements
        // at the end of the list
        // using add () method via for loops
        for (int i = 1; i <= 5; i++)
            arrli.add(i);

        // Printing the ArrayList
        System.out.println(arrli);

        // Removing an element at index 3
        // from the ArrayList
        // using remove() method
        arrli.remove(3);

        // Printing the ArrayList after
        // removing the element
        System.out.println(arrli);
    }
}
```

**Output**

```
[1, 2, 3, 4, 5]
[1, 2, 3, 5]
```

[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)是一个线性数据结构，其中元素不存储在连续的位置，每个元素都是一个单独的[对象](https://www.geeksforgeeks.org/classes-objects-java/)，具有数据部分和地址部分。这些元素使用指针和地址进行链接。每个元素都被称为一个节点。由于插入和删除的动态性和容易性，它们优于[阵列](https://www.geeksforgeeks.org/introduction-to-arrays/)。下面是一个演示 LinkedList 实现的示例。

> **注意:**这个类实现了 [**链表数据结构**](https://www.geeksforgeeks.org/data-structures/linked-list/) 。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Demonstrate Working of a LinkedList

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // main driver method
    public static void main(String args[])
    {

        // Creating an object of the
        // class linked list
        LinkedList<String> object
            = new LinkedList<String>();

        // Adding the elements to the object created
        // using add() and addLast() method

        // Custom input elements
        object.add("A");
        object.add("B");
        object.addLast("C");

        // Print the current LinkedList
        System.out.println(object);

        // Removing elements from the List object
        // using remove() and removeFirst() method
        object.remove("B");
        object.removeFirst();

        System.out.println("Linked list after "
                           + "deletion: " + object);
    }
}
```

**Output:** 

```
[A, B, C]
Linked list after deletion: [C]
```

现在在充分理解了它们之后，让我们讨论一下 Java 中的 ArrayList 和 LinkedList 之间的区别

<figure class="table">

| 数组列表 | 链接列表 |
| --- | --- |
| This class uses a dynamic array to store the elements in it. With the introduction of [generic](https://www.geeksforgeeks.org/generics-in-java/) , this class supports the storage of all types of objects. | This class uses a [doubly linked list](https://www.geeksforgeeks.org/doubly-linked-list/) to store its elements. Similar to array list, this class also supports storing all types of objects. |
| Because of the internal implementation, it takes more time to manipulate the array list. Every time we remove an element, internally, the array is traversed and the memory bits are shifted. | Compared with array list, it takes less time to operate linked list, because there is no concept of shifting memory bits in bidirectional linked list. Traverse the list and change the reference link. |
| This class implements a [list interface](https://www.geeksforgeeks.org/list-interface-java-examples/) . Therefore, this is a list. | This class implements [list interface](https://www.geeksforgeeks.org/list-interface-java-examples/) and [Deqing interface](https://www.geeksforgeeks.org/deque-interface-java-example/) . Therefore, it can be used as a list and a dege. |
| This class works better when the application requires storing and accessing data. | This class works better when applications require operations on stored data. |

</figure>