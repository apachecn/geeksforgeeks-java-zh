# Java 中抽象列表添加(int index，E 元素)方法，示例

> 原文:[https://www . geesforgeks . org/abstract list-addint-index-e-element-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-addint-index-e-element-method-in-java-with-examples/)

[抽象列表](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)的 **add(int index，E element)** 方法用于在该列表的指定位置插入一个元素。新元素被插入到列表中的指定索引处。

**语法:**

```java
public void add(int index, E element)
```

**参数:**该方法取 2 个参数:-

1.  **Index** : Specify the index to insert the element.
2.  **Element** : The element to be inserted.

**返回:**如果元素成功插入列表，函数返回布尔值*真*，否则返回*假*。

**异常:**出现的异常有:-

*   **classcasteexception** : If the class of an element of this set is incompatible with the specified set.
*   [T0】 NullPointerException 【T1]: If this collection contains null elements and the specified collection does not allow null elements, or if the specified collection is null.
*   **Operation exception** is not supported: if the list does not support adding operation.
*   [T0】 IllegalArgumentException 【T1]: If certain attributes of the specified element prevent it from being added to this list.
*   **Index out of bounds exception** : If the index is out of range (index size ()).

下面的程序说明了 AbstractList 类的 add(int index，int position)函数:

**程序 1:**

```java
// Java code to illustrate AbstractList
// add(int index, int position) method

import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {

        // Create an empty list
        // with an initial capacity
        AbstractList<Integer> list
            = new ArrayList<Integer>(5);

        // Use add() method
        // to add elements in the list
        list.add(3);
        list.add(6);
        list.add(9);
        list.add(12);

        // Prints all the elements
        // available in list
        System.out.println("Before: "
                           + list);

        // Add(int index, int element) method
        list.add(1, 4);

        // Prints all the elements
        // after the above method
        System.out.println("After: "
                           + list);
    }
}
```

**输出:**

```java
Before: [3, 6, 9, 12]
After: [3, 4, 6, 9, 12]

```

**程序二:**

```java
// Java code to illustrate AbstractList
// add(int index, int position) method

import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {

        // Create an empty list
        // with an initial capacity
        AbstractList<String> list
            = new ArrayList<String>(5);

        // Use add() method
        // to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Computer");
        list.add("Portal");

        // Prints all the elements
        // available in the list
        System.out.println("Before: " + list);

        // Add(int index, int element) method
        list.add(2, "Geeks");

        // Prints all the elements
        // after the above method
        System.out.println("After: " + list);
    }
}
```

**输出:**

```java
Before: [Geeks, for, Computer, Portal]
After: [Geeks, for, Geeks, Computer, Portal]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/abstract list . html # add(int，%20E)](https://docs.oracle.com/javase/7/docs/api/java/util/AbstractList.html#add(int, %20E))