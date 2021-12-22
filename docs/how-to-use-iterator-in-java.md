# 如何在 Java 中使用迭代器？

> 原文:[https://www.geeksforgeeks.org/how-to-use-iterator-in-java/](https://www.geeksforgeeks.org/how-to-use-iterator-in-java/)

“迭代器”是一个属于集合框架的接口。它允许我们遍历集合，访问数据元素并移除集合中的数据元素。
**java.util** 包有**公共接口迭代器**，包含三种方法:

1.  **布尔 hasNext()** :如果 Iterator 有更多元素要迭代，则返回 true。
2.  **Object next()** :它返回集合中的下一个元素，直到 hasNext()方法返回 true。如果没有下一个元素，此方法将引发“NoSuchElementException”。
3.  **void remove()** :移除集合中的当前元素。如果在调用 next()之前调用此函数，此方法将引发“IllegalStateException”。

```java
// Java code to illustrate the use of iterator
import java.io.*;
import java.util.*;

class Test {
    public static void main(String[] args)
    {
        ArrayList<String> list = new ArrayList<String>();

        list.add("A");
        list.add("B");
        list.add("C");
        list.add("D");
        list.add("E");

        // Iterator to traverse the list
        Iterator iterator = list.iterator();

        System.out.println("List elements : ");

        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");

        System.out.println();
    }
}
```

输出:

```java
List elements : 
A B C D E 
```

**列表迭代器**

Java 中的“列表迭代器”是一个迭代器，允许用户双向遍历集合。它包含以下方法:

1.  **void add(Object object)** :它在 next()函数返回的元素之前插入一个对象。
2.  **布尔 hasNext( )** :如果列表有下一个元素，则返回 true。
3.  **布尔 hasPrevious( )** :如果列表中有上一个元素，则返回 true。
4.  **Object next( )** :返回列表的下一个元素。如果列表中没有下一个元素，它将引发“NoSuchElementException”。
5.  **Object previous( )** :返回列表的上一个元素。如果没有前一个元素，它将引发“NoSuchElementException”。
6.  **void remove( )** :从列表中删除当前元素。如果在调用 next()或 previous()之前调用此函数，它将引发“IllegalStateException”。

```java
// Java code to illustrate the use of ListIterator
import java.io.*;
import java.util.*;

class Test {
    public static void main(String[] args)
    {
        ArrayList<String> list = new ArrayList<String>();

        list.add("A");
        list.add("B");
        list.add("C");
        list.add("D");
        list.add("E");

        // ListIterator to traverse the list
        ListIterator iterator = list.listIterator();

        // Traversing the list in forward direction
        System.out.println("Displaying list elements in forward direction : ");

        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");

        System.out.println();

        // Traversing the list in backward direction
        System.out.println("Displaying list elements in backward direction : ");

        while (iterator.hasPrevious())
            System.out.print(iterator.previous() + " ");

        System.out.println();
    }
}
```

输出:

```java
Displaying list elements in forward direction : 
A B C D E 
Displaying list elements in backward direction : 
E D C B A 
```

**相关文章:**

*   [Java 中的迭代器](https://www.geeksforgeeks.org/iterators-in-java/)
*   [迭代器 vs Java 中的 Foreach](https://www.geeksforgeeks.org/iterator-vs-foreach-in-java/)
*   [在 Java 中从集合中检索元素(对于每个元素，迭代器，列表迭代器&枚举迭代器)](https://www.geeksforgeeks.org/retrieving-elements-from-collection-for-each-iterator-listiterator-enumerationiterator/)

本文由 Mehak Narang 供稿。

发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息