# Java 中的 LinkedList pop()方法

> 原文:[https://www . geesforgeks . org/linked list-pop-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-pop-method-in-java/)

java.util.LinkedList.pop()方法用于从 LinkedList 表示的堆栈中移除并返回顶部元素。该方法只是弹出堆栈顶部的一个元素。该方法类似于 LinkedList 中的 [removeFirst](https://www.geeksforgeeks.org/linkedlist-removefirst-method-in-java/) 方法。

**语法**:

```
LinkedListObject.pop()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回 LinkedList 表示的栈的第一个(栈顶)值。

**异常:**如果 LinkedList 表示的堆栈中没有元素，pop 方法将抛出 *NoSuchElementException()* 。

下面的程序说明了 java.util.LinkedList.pop()方法:
**程序 1:**

```
// Java code to demonstrate pop method in LinkedList

import java.util.LinkedList;

public class GfG {
    // Main method
    public static void main(String[] args)
    {

        // Creating a LinkedList object to represent a stack.
        LinkedList<String> stack = new LinkedList<>();

        // Pushing an element in the stack
        stack.push("Geeks");

        // Pushing an element in the stack
        stack.push("for");

        // Pop an element from stack
        String s = stack.pop();

        // Printing the popped element.
        System.out.println(s);

        // Pushing an element in the stack
        stack.push("Geeks");

        // Printing the complete stack.
        System.out.println(stack);
    }
}
```

**Output:**

```
for
[Geeks, Geeks]

```

**程序 2 :**

```
// Java code to demonstrate pop method in LinkedList

import java.util.LinkedList;

public class GfG {
    // Main method
    public static void main(String[] args)
    {

        // Creating a LinkedList object to represent a stack.
        LinkedList<Integer> stack = new LinkedList<>();

        // Pushing an element in the stack
        stack.push(10);

        // Pushing an element in the stack
        stack.push(20);

        // Pop an element from stack
        Integer ele = stack.pop();

        // Printing the popped element.
        System.out.println(ele);

        // Pop an element from stack
        ele = stack.pop();

        // Printing the popped element.
        System.out.println(ele);

        // Throws NoSuchElementException
        ele = stack.pop();

        // Throwsca runtime exception
        System.out.println(ele);

        // Printing the complete stack.
        System.out.println(stack);
    }
}
```

**输出**:

```
20
10

then it will throw :
Exception in thread "main" java.util.NoSuchElementException
    at java.util.LinkedList.removeFirst(LinkedList.java:270)
    at java.util.LinkedList.pop(LinkedList.java:801)
    at GfG.main(GfG.java:35)

```