# Java 中抽象顺序列表集(int，Object)方法，示例

> 原文:[https://www . geesforgeks . org/abstractsequentialist-set int-object-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-setint-object-method-in-java-with-example/)

**Java 抽象顺序列表**的 **set()** 方法用于将使用抽象顺序列表类创建的列表中的任何特定元素替换为另一个元素。这可以通过在 set()方法的参数中指定要替换的元素和新元素的位置来实现。

**语法:**

```java
public E set(int index, Object element)

```

**参数:**该函数接受两个参数，如上语法所示，如下所述。

*   **索引**:这是整数类型，指的是列表中要替换的元素的位置。
*   **元素**:是替换现有元素的新元素，与列表对象类型相同。

**返回值:**该方法返回列表中被新值替换的前一个值。

**异常:**该方法抛出以下异常:

*   **不支持操作异常**:如果该列表不支持设置操作
*   **ClassCastException** :如果指定元素的类阻止其添加到该列表中
*   **NullPointerException** :如果指定的元素为空，并且该列表不允许空元素
*   **IllegalArgumentException** :如果指定元素的某些属性阻止其添加到此列表中
*   **IndexOutOfBoundsException**:如果索引超出范围(索引=大小())

下面的程序说明了 Java . util . abstractsequentialilist . set()方法:

**例 1:**

```java
// Java code to illustrate set()

import java.io.*;
import java.util.*;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String> list
            = new LinkedList<String>();

        // Use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Displaying the linkedlist
        System.out.println("AbstractSequentialList:"
                           + list);

        // Using set() method to replace Geeks with GFG
        System.out.println("The Object that is replaced is: "
                           + list.set(2, "GFG"));

        // Using set() method to replace 20 with 50
        System.out.println("The Object that is replaced is: "
                           + list.set(4, "50"));

        // Displaying the modified linkedlist
        System.out.println("The new AbstractSequentialList is:"
                           + list);
    }
}
```

**Output:**

```java
AbstractSequentialList:[Geeks, for, Geeks, 10, 20]
The Object that is replaced is: Geeks
The Object that is replaced is: 20
The new AbstractSequentialList is:[Geeks, for, GFG, 10, 50]

```

**示例 2:** 演示 IndexOutOfBoundException

```java
// Java code to illustrate set()

import java.io.*;
import java.util.*;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String> list
            = new LinkedList<String>();

        // Use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Displaying the linkedlist
        System.out.println("AbstractSequentialList:"
                           + list);

        // Using set() method to replace 10th with GFG
        // and the 10th element does not exist
        System.out.println("Trying to replace 10th "
                           + "element with GFG");

        try {
            list.set(10, "GFG");
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
AbstractSequentialList:[Geeks, for, Geeks, 10, 20]
Trying to replace 10th element with GFG
java.lang.IndexOutOfBoundsException: Index: 10, Size: 5

```