# Java 中迭代器和拆分器的区别

> 原文:[https://www . geesforgeks . org/Java 中迭代器和拆分器的区别/](https://www.geeksforgeeks.org/difference-between-iterator-and-spliterator-in-java/)

Java **迭代器**接口表示一个能够遍历一组 Java 对象的对象，一次一个对象。迭代器接口是 Java 中最古老的对象集合迭代机制之一(虽然不是最古老的——枚举器早于迭代器)。

***此外，迭代器在两个方面不同于枚举:***

**1。**迭代器允许调用方在元素迭代期间从指定集合中移除给定元素。

**2。**方法名称得到增强。

## 爪哇

```
// Java program to illustrate Iterator interface

import java.util.Iterator;
import java.util.LinkedList;
import java.util.List;
public class JavaIteratorExample1 {
    public static void main(String[] args)
    {

        // create a linkedlist
        List<String> list = new LinkedList<>();

        // Add elements
        list.add("Welcome");
        list.add("to");
        list.add("our");
        list.add("website");

        // print the list to the console
        System.out.println("The list is given as : "
                           + list);

        // call iterator on the list
        Iterator<String> itr = list.iterator();

        // itr.hasNext() returns true if there
        // is still an element next to the current
        // element pointed by iterator
        while (itr.hasNext()) {

            // Returns the next element.
            System.out.println(itr.next());
        }

        // Removes the last element.
        itr.remove();

        // print the list after removing an
        // element
        System.out.println(
            "After the remove() method is called : "
            + list);
    }
}
```

**输出**

```
The list is given as : [Welcome, to, our, website]
Welcome
to
our
website
After the remove() method is called : [Welcome, to, our]

```