# 如何在 Java 中迭代 LinkedList？

> 原文:[https://www . geesforgeks . org/how-iterate-linked list-in-Java/](https://www.geeksforgeeks.org/how-to-iterate-linkedlist-in-java/)

[Java 中的 LinkedList](https://www.geeksforgeeks.org/linked-list-in-java/) 基本上是 java.util 包中存在的集合框架的一部分。它是 LinkedList 数据结构的实现，在内存中以不连续的方式存储元素。

**迭代链表的五种方法是:**

1.  Use for loop
2.  Use while loop
3.  Use enhanced for loop
4.  Using iterators
5.  Use the forEach () method

**方法一:使用 For**[**Loop**](https://www.geeksforgeeks.org/loops-in-java/)

## Java

```
// Java program for iterating the LinkedList
// using For loop

import java.util.LinkedList;

public class GFG {
    public static void main(String[] args)
    {

        // Creating a LinkedList of Integer type
        LinkedList<Integer> linkedList = new LinkedList<>();

        // Inserting some Integer values to our LinkedList
        linkedList.add(40);
        linkedList.add(44);
        linkedList.add(80);
        linkedList.add(9);

        // LinkedList after insertions: [40, 44, 80, 9]

        // Calling the function to iterate our LinkedList
        iterateUsingForLoop(linkedList);
    }

    // Function to iterate the LinkedList using a simple for
    // loop
    public static void
             iterateUsingForLoop(LinkedList<Integer> linkedList)
    {

        System.out.print(
            "Iterating the LinkedList using a simple for loop : ");

        for (int i = 0; i < linkedList.size(); i++) {
            System.out.print(linkedList.get(i) + " ");
        }
    }
}
```

**输出**

```
Iterating the LinkedList using a simple for loop : 40 44 80 9
```