# Java 中的 LinkedList push()方法

> 原文:[https://www . geesforgeks . org/linked list-push-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-push-method-in-java/)

java.util.LinkedList.push()方法用于在 LinkedList 表示的堆栈的开始(顶部)推送元素。这类似于 LinkedList 的 [addFirst()](https://contribute.geeksforgeeks.org/geek/linkedlist-addfirst-method-in-java/) 方法，只是在链表的第一个位置或顶部插入元素。

**语法**:

```java
LinkedListObject.push(Object element)

```

**参数:**该方法接受一个对象类型的参数*元素*，表示要插入的元素。类型“对象”应该是由链接列表表示的同一堆栈。

**返回类型:**该方法的返回类型为 void，即不返回任何值。

下面的程序说明了 java.util.LinkedList.push()方法:

**程序 1:**

```java
// Java code to demonstrate push() method
import java.util.LinkedList;

public class GfG {
    // Main method
    public static void main(String[] args)
    {

        // Creating a LinkedList object to represent a stack.
        LinkedList<String> stack = new LinkedList<>();

        // Pushing an element in the stack
        stack.push("I");

        // Pushing an element in the stack
        stack.push("Like");

        // Pushing an element in the stack
        stack.push("GeeksforGeeks");

        // Printing the complete stack.
        System.out.println(stack);
    }
}
```

**Output:**

```java
[GeeksforGeeks, Like, I]

```

**程序 2 :**

```java
// Java code to demonstrate push() method

import java.util.LinkedList;

public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Creating a LinkedList object to represent a stack.
        LinkedList<Integer> stack = new LinkedList<>();

        // Pushing an element in the stack
        stack.push(30);

        // Pushing an element in the stack
        stack.push(20);

        // Pushing an element in the stack
        stack.push(10);

        // Printing the complete stack.
        System.out.println(stack);
    }
}
```

**Output:**

```java
[10, 20, 30]

```