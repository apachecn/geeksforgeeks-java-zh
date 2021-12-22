# 用示例链接 Java 中的 List 元素()方法

> 原文:[https://www . geeksforgeeks . org/linked list-element-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedlist-element-method-in-java-with-examples/)

**[Java . util . linkedlist](https://www.geeksforgeeks.org/linked-list-in-java/)**类的**元素()**方法检索但不移除该列表的头部(第一个元素)。

**语法:**

```
public E element()
```

**返回值:**该方法返回该列表的**头**。

以下是说明*元素()*方法的示例

**例 1:**

```
// Java program to demonstrate
// element() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of LinkedList<Integer>
            LinkedList<Integer> list = new LinkedList<Integer>();

            // add some elements to list
            list.add(10);
            list.add(20);
            list.add(30);

            // print the linked list
            System.out.println("LinkedList : " + list);

            // getting the head of list
            // using element() method
            int value = list.element();

            // print the head of list
            System.out.println("Head of list : " + value);
        }

        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
LinkedList : [10, 20, 30]
Head of list : 10

```

**例 2:**

```
// Java program to demonstrate
// element() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of LinkedList<String>
            LinkedList<String> list = new LinkedList<String>();

            // add some elements to list
            list.add("A");
            list.add("B");
            list.add("C");

            // print the linked list
            System.out.println("LinkedList : " + list);

            // getting the head of list
            // using element() method
            String value = list.element();

            // print the head of list
            System.out.println("Head of list : " + value);
        }

        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
LinkedList : [A, B, C]
Head of list : A

```