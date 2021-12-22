# Java 中的 CopyOnWriteArrayList addAll()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-addall-method-in-java-with-examples/)

### 布尔地址(集合 c)

该方法用于将集合 **c** 标识的所有元素追加到列表的末尾，顺序与集合的迭代器返回的顺序相同。

**参数:**这个方法接受一个强制参数 **c** ，它是包含元素的集合，这些元素将被附加在列表的末尾。

**返回值:**这个方法返回一个布尔值。如果集合被正确插入列表，则返回 true，否则返回 false。

**异常:**如果指定的元素为空，该方法抛出**空指针异常**。

```java
// Java Program to illustrate the
// CopyOnWriteArrayList.addAll(Collection c)

import java.io.*;
import java.util.concurrent.CopyOnWriteArrayList;

public class CopyOnWriteArrayListDemo {
    public static void main(String args[])
    {

        // create an empty array list1 with initial
        // capacity as 5
        CopyOnWriteArrayList<Integer> list1
            = new CopyOnWriteArrayList<Integer>();

        // use add() method to add elements in the list
        list1.add(12);
        list1.add(20);
        list1.add(45);

        // prints all the elements available in list1
        System.out.println("Printing list1:");
        for (Integer number : list1)
            System.out.println("Number = " + number);

        // create an empty array list2 with an initial
        // capacity
        CopyOnWriteArrayList<Integer> list2
            = new CopyOnWriteArrayList<Integer>();

        // use add() method to add elements in list2
        list2.add(25);
        list2.add(30);
        list2.add(31);
        list2.add(35);

        // let us print all the elements available in
        // list2
        System.out.println("Printing list2:");
        for (Integer number : list2)
            System.out.println("Number = " + number);

        // inserting all elements, list2 will get printed
        // after list1
        list1.addAll(list2);

        System.out.println("Printing all the elements");
        // let us print all the elements available in
        // list1
        for (Integer number : list1)
            System.out.println("Number = " + number);
    }
}
```

**Output:**

```java
Printing list1:
Number = 12
Number = 20
Number = 45
Printing list2:
Number = 25
Number = 30
Number = 31
Number = 35
Printing all the elements
Number = 12
Number = 20
Number = 45
Number = 25
Number = 30
Number = 31
Number = 35

```

### 布尔地址(整数索引，集合 c)

这个方法是将一个集合的元素添加到另一个列表中。元素的插入将从指定的索引开始。元素将按照集合迭代器返回的顺序添加。当添加新元素时，以前出现在索引中的元素(如果有)将向右移动。

**参数:**
**索引**是集合元素插入的位置。
**c** 是包含元素的集合，这些元素将被附加在列表的末尾。

**返回值:**其返回类型为布尔值。如果集合被正确插入到指定索引处的列表中，则返回 true，否则返回 false。

**异常:**
空指针异常–如果指定的集合为空。
IndexOutOfBoundsException–如果指定的索引超出范围。

```java
// Java Program to illustrate the CopyOnWriteArrayList
// addAll(Collection c)
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class CopyOnWriteArrayListDemo {
    public static void main(String args[])
    {

        // create an empty array list1 with initial
        // capacity 5
        CopyOnWriteArrayList<Integer> list
            = new CopyOnWriteArrayList<Integer>();

        // using add() method to add elements in the
        // list
        list.add(12);
        list.add(20);
        list.add(45);

        // prints all the elements available in list1
        System.out.println("Printing list1:");
        for (Integer number : list)
            System.out.println("Number = " + number);

        // create an empty array list2 with an initial
        // capacity
        CopyOnWriteArrayList<Integer> list2
            = new CopyOnWriteArrayList<Integer>();

        // use add() method to add elements in list2
        list2.add(25);
        list2.add(30);
        list2.add(31);
        list2.add(35);

        // prints all the elements available in list2
        System.out.println("Printing list2:");
        for (Integer number : list2)
            System.out.println("Number = " + number);

        // inserting all elements of list2 at third
        // position
        list.addAll(2, list2);

        System.out.println("Printing all the elements");

        // prints all the elements available in list1
        for (Integer number : list)
            System.out.println("Number = " + number);
    }
}
```

**Output:**

```java
Printing list1:
Number = 12
Number = 20
Number = 45
Printing list2:
Number = 25
Number = 30
Number = 31
Number = 35
Printing all the elements
Number = 12
Number = 20
Number = 25
Number = 30
Number = 31
Number = 35
Number = 45

```