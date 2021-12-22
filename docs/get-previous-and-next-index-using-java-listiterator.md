# 使用 Java 列表迭代器获取上一个和下一个索引

> 原文:[https://www . geesforgeks . org/get-previous-and-next-index-using-Java-listiterator/](https://www.geeksforgeeks.org/get-previous-and-next-index-using-java-listiterator/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)中的上一个索引和下一个索引可以分别使用列表迭代器接口的方法 previous index()和 next index()获得。如果 previousIndex()位于列表的开头，它也可以返回-1。

**示例:**

```java
Input: list = [2, 3, 6, 8]
listiterator is at the beginning find previous index.

Output: -1

Input: list = [2, 3, 6, 8]
listiterator is at the beginning find next index.
```

**使用 previousIndex()和 nextIndex()的步骤:**

*   创建一个空数组列表
*   向数组列表中添加元素。
*   使用[列表迭代器()](https://www.geeksforgeeks.org/arraylist-listiterator-method-in-java-with-examples/)方法创建一个列表迭代器。

```java
Listiterator<Integer>iterator = arrList.listIterator();
```

*   现在使用下面的命令获取所需的索引

**语法**

```java
iterator.previousIndex();
```

**返回:** 元素的索引，该索引将通过后续调用先前的返回，或者如果列表迭代器位于列表的开头则返回-1

**语法**

```java
iterator.nextIndex();
```

**返回:**后续调用 next 将返回的元素的索引，如果列表迭代器在列表的末尾，则返回列表大小

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to get Previous and
// next index using ListIterator

import java.io.*;
import java.util.ArrayList;
import java.util.ListIterator;

class PreviousAndNextIndex {

    public static void main(String[] args)
    {
        // create empty ArrayList
        ArrayList<Integer> arrList
            = new ArrayList<Integer>();

        // add elements to the ArrayList
        arrList.add(5);
        arrList.add(10);
        arrList.add(15);
        arrList.add(20);
        arrList.add(25);
        arrList.add(30);

        // print the initial list
        System.out.println("Initial arraylist =>"
                           + arrList);

        // initializing ListIterator
        ListIterator<Integer> iterator
            = arrList.listIterator();

        // initially iterator is the beginning so
        // previousIndex() will return -1
        System.out.println("previous index =>"
                           + iterator.previousIndex());

        // from -1 moving iterator to the 1st index
        iterator.next();
        iterator.next();

        // now iterator is at 1st index 
        // so nextIterator() will return 2
        System.out.println("Next index =>"
                           + iterator.nextIndex());
    }
}
```

**输出:**

```java
Initial arraylist =>[5, 10, 15, 20, 25, 30]
previous index =>-1
Next index =>2
```