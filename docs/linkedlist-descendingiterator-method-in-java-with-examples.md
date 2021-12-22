# 用示例链接 Java 中的链表下降器()方法

> 原文:[https://www . geeksforgeeks . org/linked list-dependingiterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedlist-descendingiterator-method-in-java-with-examples/)

**[Java . util . LinkedList](https://www.geeksforgeeks.org/linked-list-in-java/)**类的**dependingiterator()**方法用于以相反的顺序返回该 linked list 中元素的迭代器。元素将按从最后(尾部)到第一(头部)的顺序返回。

**语法:**

```
public Iterator descendingIterator()
```

**返回值:**这个方法返回一个**迭代器**在这个链表中的元素上以相反的顺序。

下面是说明*下降法的例子*

**例 1:**

```
// Java program to demonstrate
// descendingIterator() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of TreeMap<Integer, String>
            LinkedList<String> list = new LinkedList<String>();

            // add some elements to list
            list.add("A");
            list.add("B");
            list.add("C");

            // print the linked list
            System.out.println("LinkedList:" + list);

            // set Iterator as descending
            // using descendingIterator() method
            Iterator x = list.descendingIterator();

            // print list with descending order
            while (x.hasNext()) {
                System.out.println("Value is : "
                                   + x.next());
            }
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**Output:**

```
LinkedList:[A, B, C]
Value is : C
Value is : B
Value is : A

```

**例 2:**

```
// Java program to demonstrate
// descendingIterator() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of TreeMap<Integer, String>
            LinkedList<Integer>
                list = new LinkedList<Integer>();

            // add some elements to list
            list.add(10);
            list.add(20);
            list.add(30);

            // print the linked list
            System.out.println("LinkedList:" + list);

            // set Iterator as descending
            // using descendingIterator() method
            Iterator x = list.descendingIterator();

            // print list with descending order
            while (x.hasNext()) {
                System.out.println("Value is : "
                                   + x.next());
            }
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
LinkedList:[10, 20, 30]
Value is : 30
Value is : 20
Value is : 10

```