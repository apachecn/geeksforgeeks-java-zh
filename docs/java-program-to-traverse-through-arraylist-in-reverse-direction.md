# 反向遍历数组列表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-反向遍历数组列表/](https://www.geeksforgeeks.org/java-program-to-traverse-through-arraylist-in-reverse-direction/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)是集合框架的一部分，存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中。它为我们提供了 Java 中的动态数组，就像 C++中的 Vector 一样。尽管它可能比标准数组慢，但在需要对数组进行大量操作的程序中会很有帮助。任务是在数组列表中插入一个元素，然后反转它，或者说反转方向。

**例:**

```java
Input :1, 2, 3, 4, 5, 6 
Output :  6, 5, 4, 3, 2, 1 

Input :  10, 22, 34, 3, 2, 6
Output :  6, 2, 3, 34, 22, 10 

Input :  11, 22, 34, 42, 51 , 63
Output :  63, 51, 42, 34, 22, 11
```

有几种方法可以让我们以下面列出的相反方向迭代和打印列表。

**方法 1:(使用列表迭代器)**

**1。**声明数组列表

```java
// size of n
ArrayList<Integer> List  = new ArrayList<Integer>(n);
```

**2。**通过使用 add 函数，我们将元素推入数组列表。

**3。**使用迭代器到达数组列表遍历的最后一个元素后。hasPrevious()方法返回 true 如果一个元素出现在当前元素的后面，遍历直到 hasPrevious()返回 false。

**4。**遍历时打印数组列表的当前元素。

## Java

```java
// Traverse through ArrayList in 
// reverse direction using List 
// Iterator in Java

import java.util.ListIterator;
import java.io.*;
import java.util.ArrayList;

class GFG {
    public static void main(String[] args)
    {
        // create an instance of arraylist
        ArrayList<Integer> List = new ArrayList<Integer>();

        // add elements
        List.add(10);
        List.add(9);
        List.add(8);
        List.add(7);
        List.add(6);

        // create a listiterator on list
        ListIterator<Integer> List_Iterator
            = List.listIterator(List.size());

        System.out.println("Reversed : ");

        // print ArrayList in reverse direction using
        // listiterator
        while (List_Iterator.hasPrevious()) {
            System.out.println(List_Iterator.previous());
        }
    }
}
```

**输出**

```java
Reversed : 
6
7
8
9
10
```

**方法 2:(使用流)**

[流应用编程接口](https://www.geeksforgeeks.org/stream-in-java/)用于处理对象集合。流是支持各种方法的对象序列，这些方法可以通过流水线来产生所需的结果。

*   Use List.stream () to get the stream.
*   Use **stream.collect ()** to collect the elements of this stream into [link list](https://www.geeksforgeeks.org/linked-list-in-java/) .
*   Use the LinkedList.descendingIterator () method to iterate the linked list in the reverse order.
*   Use forEachRemaining () to print each element of the array list. We can provide the method reference **system.out:: println** iterator to forEachRemaining ().

## 爪哇

```java
// Traverse through ArrayList in
// reverse direction Using
// stream in Java

import java.lang.*;
import java.util.stream.*;
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // create a list
        List<Integer> Arlist = Arrays.asList(5, 2, 4, 8);
        System.out.println("Reversed : ");

        // create a stream
        // collect the elements after these operations
        // create a descending iterator on the stream
        // loop through the descending iterator
        // print the element
        Arlist.stream()
            .collect(
                Collectors.toCollection(LinkedList::new))
            .descendingIterator()
            .forEachRemaining(System.out::println);
    }
}
```

**输出**

```java
Reversed : 
8
4
2
5
```

**方法三:(使用 For 循环)**我们知道[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)是一个有序集合，我们只需要通过它的索引就可以访问列表的元素，所以定义一个 ArrayList，从最后使用一个 [for 循环](https://www.geeksforgeeks.org/java-for-loop-with-examples/)迭代到第一个元素，打印每个元素。

## Java

```java
// Traverse through ArrayList in
// reverse direction using For
// Loop in Java
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // create a list
        List<Integer> Arlist = Arrays.asList(5, 4, 8, 2);

        System.out.println("Reversed :");

        // Printing in reverse
        for (int i = Arlist.size() - 1; i >= 0; i--) {
            System.out.println(Arlist.get(i));
        }
    }
}
```

**输出**

```java
Reversed :
2
8
4
5
```

**方法 4:(使用 Apache Common 的 reverselistitator)**

这个方法提供了 ReverseListIterator，我们可以用它以相反的顺序迭代 List。当我们使用 ReverseListIterator 时，next()将返回数组列表中的最后一个元素，当我们调用下一个元素时，下一个括号将返回当前元素的前一个元素，而 has next 将检查我们的数组列表是否包含元素。

## 爪哇

T0T6】

**输出**

```java
Reversed :
7
8
5
1
```

**时间复杂度:** O(n)