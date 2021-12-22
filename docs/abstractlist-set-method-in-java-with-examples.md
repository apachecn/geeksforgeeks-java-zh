# Java 中的抽象列表集()方法，示例

> 原文:[https://www . geesforgeks . org/abstract list-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-set-method-in-java-with-examples/)

**[Java . util . AbstractList](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的 **set()** 方法用于将使用 abstract list 类创建的抽象列表中的任何特定元素替换为另一个元素。这可以通过在 set()方法的参数中指定要替换的元素和新元素的位置来实现。

**语法:**

```java
AbstractList.set(*int index, Object element*)
```

**参数:**该函数接受两个参数，如下所述:

*   **索引**:这是整数类型，指的是要从抽象列表中替换的元素的位置。
*   **元素**:是替换现有元素的新元素，与抽象列表的对象类型相同。

**返回值:**该方法返回抽象列表中被新值替换的前一个值。

下面的程序说明了 AbstractList.set()方法:

```java
// Java code to illustrate set()

import java.util.*;
import java.util.LinkedList;

public class AbstractListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractList
        AbstractList<String> list = new LinkedList<String>();

        // Use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Displaying the AbstractList
        System.out.println("AbstractList:" + list);

        // Using set() method to replace Geeks with GFG
        System.out.println("The Object that is replaced is: "
                           + list.set(2, "GFG"));

        // Using set() method to replace 20 with 50
        System.out.println("The Object that is replaced is: "
                           + list.set(4, "50"));

        // Displaying the modified AbstractList
        System.out.println("The new AbstractList is:" + list);
    }
}
```

**Output:**

```java
AbstractList:[Geeks, for, Geeks, 10, 20]
The Object that is replaced is: Geeks
The Object that is replaced is: 20
The new AbstractList is:[Geeks, for, GFG, 10, 50]

```

**程序 2:**

```java
// Java code to illustrate set()

import java.util.*;

public class LinkedListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractList
        AbstractList<Integer>
            list = new LinkedList<Integer>();

        // Use add() method to add elements in the list
        list.add(10);
        list.add(20);
        list.add(30);
        list.add(40);
        list.add(50);

        // Displaying the AbstractList
        System.out.println("AbstractList:" + list);

        // Using set() method to replace 10 with 100
        System.out.println("The Object that is replaced is: "
                           + list.set(0, 100));

        // Using set() method to replace 20 with 200
        System.out.println("The Object that is replaced is: "
                           + list.set(1, 200));

        // Displaying the modified AbstractList
        System.out.println("The new AbstractList is:" + list);
    }
}
```

**Output:**

```java
AbstractList:[10, 20, 30, 40, 50]
The Object that is replaced is: 10
The Object that is replaced is: 20
The new AbstractList is:[100, 200, 30, 40, 50]

```