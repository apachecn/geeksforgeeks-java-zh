# Java 中的抽象顺序列表添加所有()方法，带示例

> 原文:[https://www . geesforgeks . org/abstractsequentialist-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractsequentiallist-addall-method-in-java-with-examples/)

[**【抽象顺序列表】**](https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/) 的 **addAll(int index，Collection C)** 方法用于将集合中作为参数传递的所有元素追加到抽象顺序列表的特定索引或位置。

**语法:**

```java
boolean addAll(int index, Collection C)
```

**参数:**该函数接受两个参数，如上语法所示，描述如下。

*   **索引**:该参数为整数数据类型，指定列表中从容器元素插入位置开始的位置。
*   **C** :是需要追加元素的集合。

**返回值:**如果至少执行了一个追加操作，则该方法返回真。

下面的程序说明了 Java . util . abstractsequentialist . addall()方法:

**例 1:**

```java
// Java code to illustrate addAll() method

import java.util.*;
import java.util.AbstractSequentialList;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String>
            absqlist = new LinkedList<String>();

        // Use add() method to add elements
        absqlist.add("Geeks");
        absqlist.add("for");
        absqlist.add("Geeks");
        absqlist.add("10");
        absqlist.add("20");

        // Creating a Collection
        Collection<String>
            collect = new ArrayList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");
        collect.add("for");
        collect.add("Geeks");

        // Displaying the list
        System.out.println("AbstractSequentialList: "
                           + absqlist);

        // Appending the collection to the list
        absqlist.addAll(1, collect);

        // Clearing the list using clear() and displaying
        System.out.println("The new list is: "
                           + absqlist);
    }
}
```

**Output:**

```java
AbstractSequentialList: [Geeks, for, Geeks, 10, 20]
The new list is: [Geeks, A, Computer, Portal, for, Geeks, for, Geeks, 10, 20]

```

**例 2:**

```java
// Java code to illustrate boolean addAll()

import java.util.*;
import java.util.AbstractSequentialList;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractSequentialList
        AbstractSequentialList<Integer>
            absqlist = new LinkedList<Integer>();

        // Use add() method to add elements
        absqlist.add(10);
        absqlist.add(20);
        absqlist.add(30);
        absqlist.add(10);
        absqlist.add(20);

        // Creating a Collection
        Collection<Integer>
            collect = new LinkedList<Integer>();
        collect.add(1);
        collect.add(2);
        collect.add(3);
        collect.add(4);
        collect.add(5);

        // Displaying the list
        System.out.println("The AbstractSequentialList is: "
                           + absqlist);

        // Appending the collection to the list
        absqlist.addAll(1, collect);

        // Clearing the list using clear() and displaying
        System.out.println("The new list is: " + absqlist);
    }
}
```

**Output:**

```java
The AbstractSequentialList is: [10, 20, 30, 10, 20]
The new list is: [10, 1, 2, 3, 4, 5, 20, 30, 10, 20]

```