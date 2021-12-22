# Java abstractsequentialist | ListIterator()

> 原文:[https://www . geesforgeks . org/Java-abstractsequentialist-listiterator/](https://www.geeksforgeeks.org/java-abstractsequentiallist-listiterator/)

[**抽象顺序列表**](https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/) **列表迭代器():**Java 中的方法用来获取这个列表的列表迭代器。它返回列表中元素的列表迭代器(按正确的顺序)。

**语法:**

```
public abstract ListIterator listIterator(int index)
```

**参数:**这个方法接受一个参数**索引**，它是从列表迭代器返回的第一个元素的索引(通过调用下一个方法)

**返回:**该方法返回列表中元素的列表迭代器(按正确的顺序)。

**异常:**如果索引超出范围(索引大小())，此方法将抛出**indexout of boundsexception**

下面是演示 ListIterator()的代码:

**程序 1:**

```
// Java program to demonstrate
// add() method

import java.util.*;

public class GfG {

    public static void main(String[] args)
    {
        // Creating an instance of the AbstractSequentialList
        AbstractSequentialList<Integer> absl = new LinkedList<>();

        // adding elements to absl
        absl.add(5);
        absl.add(6);
        absl.add(7);
        absl.add(2, 8);
        absl.add(2, 7);
        absl.add(1, 9);
        absl.add(4, 10);

        // Getting ListIterator
        ListIterator<Integer> Itr = absl.listIterator(2);

        // Traversing elements
        while (Itr.hasNext()) {
            System.out.print(Itr.next() + " ");
        }
    }
}
```

**Output:**

```
6 7 10 8 7

```

**程序 2:** 演示 IndexOutOfBoundException

```
// Java code to show IndexOutofBoundException

import java.util.*;

public class GfG {

    public static void main(String[] args)
    {

        // Creating an instance of the AbstractSequentialList
        AbstractSequentialList<Integer> absl = new LinkedList<>();

        // adding elements to absl
        absl.add(5);
        absl.add(6);
        absl.add(7);
        absl.add(2, 8);
        absl.add(2, 7);
        absl.add(1, 9);
        absl.add(4, 10);

        // Printing the list
        System.out.println(absl);

        try {
            // showing IndexOutOfBoundsException
            // Getting ListIterator
            ListIterator<Integer> Itr = absl.listIterator(15);

            // Traversing elements
            while (Itr.hasNext()) {
                System.out.print(Itr.next() + " ");
            }
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
[5, 9, 6, 7, 10, 8, 7]
Exception: java.lang.IndexOutOfBoundsException: Index: 15, Size: 7

```