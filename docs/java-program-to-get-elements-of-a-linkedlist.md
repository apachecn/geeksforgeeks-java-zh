# 获取链表元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-elements-of-a-linked list/](https://www.geeksforgeeks.org/java-program-to-get-elements-of-a-linkedlist/)

[**链表**](https://www.geeksforgeeks.org/data-structures/linked-list/)**是一种线性数据结构，其中元素不存储在连续的存储位置。这里的任务是获取链表的元素。**

****1。**我们可以使用 **get(int variable)方法**从 LinkedList 的特定索引中访问元素:**

**在给定的例子中，我们已经使用了 [**得到(I)的方法**](https://www.geeksforgeeks.org/linkedlist-get-method-in-java/) **。**这里，该方法返回位于第 ***i*** <sup>th</sup> 索引处的元素。**

****语法:****

```
LinkedList.get(int index)
```

****参数:**参数*索引*是整数数据类型，指定要从链接列表中提取的元素的位置或索引。**

****返回值:**该方法返回出现在参数*索引*指定位置的元素。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to get the elements of Linkedlist

import java.io.*;
import java.util.LinkedList;
class GFG {
    public static void main(String[] args)
    {

        // Creating LinkedList
        LinkedList<String> gfg = new LinkedList<String>();

        // Adding values
        gfg.add("GEEKS");
        gfg.add("FOR");
        gfg.add("GEEKS");

        System.out.println("LinkedList Elements : ");

        for (int i = 0; i < gfg.size(); i++) {

            // get(i) returns element present at index i
            System.out.println("Element at index " + i
                               + " is: " + gfg.get(i));
        }
    }
}
```

****Output**

```
LinkedList Elements : 
Element at index 0 is: GEEKS
Element at index 1 is: FOR
Element at index 2 is: GEEKS
```** 

****2。**我们可以使用 [**迭代器()**](https://www.geeksforgeeks.org/iterators-in-java/) **方法****

*   **要使用这个方法，我们必须导入 **java.util.Iterator** 包。**
*   **在这个方法中，我们可以迭代 LinkedList，然后相应地提取给定索引处的元素。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to iterate over linkedlist
// to extract elements of linkedlist

import java.io.*;
import java.util.LinkedList;
import java.util.Iterator;
class GFG {
    public static void main(String[] args)
    {

        LinkedList<String> gfg = new LinkedList<String>();

        // Adding elements
        gfg.add("GEEKS");
        gfg.add("FOR");
        gfg.add("GEEKS");

        // Create an object of Iterator
        Iterator<String> i = gfg.iterator();

        System.out.print(
            "The elements of the input LinkedList: \n");

        int j = 0;

        // has.next() returns true if there is a next
        // element
        while (i.hasNext()) {

            System.out.print("The element at the index " + j
                             + " ");

            // next() returns the next element
            String str = i.next();

            System.out.print(str);
            System.out.print(" \n");

            ++j;
        }
    }
}
```

****Output**

```
The elements of the input LinkedList: 
The element at the index 0 GEEKS 
The element at the index 1 FOR 
The element at the index 2 GEEKS
```** 

****3。**我们可以使用[T3【列表迭代器()T5【方法】T6。](https://www.geeksforgeeks.org/linkedlist-listiterator-method-in-java/)**

*   ****ListIterator()** 是 Iterator()方法的**子接口。****
*   **它为我们提供了访问列表元素的功能。**
*   **它是双向的，这意味着它允许我们在两个方向上迭代列表的元素。**
*   **要使用这个方法，我们必须导入***Java . util . ListIterator .*****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to iterate over the
// linkedlist using listIterator()

import java.io.*;
import java.util.LinkedList;
import java.util.ListIterator;

class GFG {
    public static void main(String[] args)
    {

        LinkedList<String> gfg = new LinkedList<String>();

        // Adding elements
        gfg.add("GEEKS");
        gfg.add("FOR");
        gfg.add("GEEKS");

        // Create an object of ListIterator
        ListIterator<String> li = gfg.listIterator();

        System.out.print(
            "The elements of the LinkedList: \n");

        // hasNext() returns true if there is next element
        int j = 0;

        while (li.hasNext()) {

            // next() returns the next element
            System.out.print("The element at the index " + j
                             + " ");

            System.out.print(li.next());

            System.out.print("\n");

            ++j;
        }
        --j;

        // Now to show that ListIterator() can traverse in
        // both the direction
        System.out.print(
            "\nThe elements of the LinkedList in Reverse order: \n");

        // hasprevious() checks if there is a previous
        // element
        while (li.hasPrevious()) {

            System.out.print("The element at the index " + j
                             + " ");

            // previous() returns the previous element
            System.out.print(li.previous());
            System.out.print("\n");

            --j;
        }
    }
}
```

****Output**

```
The elements of the LinkedList: 
The element at the index 0 GEEKS
The element at the index 1 FOR
The element at the index 2 GEEKS

The elements of the LinkedList in Reverse order: 
The element at the index 2 GEEKS
The element at the index 1 FOR
The element at the index 0 GEEKS

```**