# Java 中的抽象顺序列表集合()方法，示例

> 原文:[https://www . geesforgeks . org/abstractsequentialist-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractsequentiallist-set-method-in-java-with-examples/)

**Java . util . abstractsequentialist**的 **set()** 方法用于将使用 LinkedList 类创建的序列列表中的任何特定元素替换为另一个元素。这可以通过在 set()方法的参数中指定要替换的元素和新元素的位置来实现。

**语法:**

```
AbstractSequentialList.set(int index, Object element)

```

**参数:**该函数接受两个参数，如上语法所示，如下所述。

*   **索引**:这是整数类型，指的是列表中要替换的元素的位置。
*   **元素**:是替换现有元素的新元素，与顺序列表的对象类型相同。

**返回值:**该方法返回序列列表中被新值替换的前一个值。

下面的程序说明了 Java . util . abstractsequentialilist . set()方法:

**例 1:**

```
// Java code to illustrate set()

import java.util.*;
import java.util.AbstractSequentialList;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String>
            absqlist = new LinkedList<String>();

        // Use add() method to add elements in the list
        absqlist.add("Geeks");
        absqlist.add("for");
        absqlist.add("Geeks");
        absqlist.add("10");
        absqlist.add("20");

        // Displaying the AbstractSequentialList
        System.out.println("AbstractSequentialList:"
                           + absqlist);

        // Using set() method to replace Geeks with GFG
        System.out.println("The Object that is replaced is: "
                           + absqlist.set(2, "GFG"));

        // Using set() method to replace 20 with 50
        System.out.println("The Object that is replaced is: "
                           + absqlist.set(4, "50"));

        // Displaying the modified linkedlist
        System.out.println("The new List is:" + absqlist);
    }
}
```

**Output:**

```
AbstractSequentialList:[Geeks, for, Geeks, 10, 20]
The Object that is replaced is: Geeks
The Object that is replaced is: 20
The new List is:[Geeks, for, GFG, 10, 50]

```

**例 2:**

```
// Java code to illustrate set()

import java.util.*;
import java.util.AbstractSequentialList;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractSequentialList
        AbstractSequentialList<Integer>
            absqlist = new LinkedList<Integer>();

        // Use add() method to add elements in the list
        absqlist.add(50);
        absqlist.add(40);
        absqlist.add(30);
        absqlist.add(20);
        absqlist.add(10);

        // Displaying the AbstractSequentialList
        System.out.println("AbstractSequentialList:"
                           + absqlist);

        // Using set() method to replace 40 with 400
        System.out.println("The Object that is replaced is: "
                           + absqlist.set(1, 400));

        // Using set() method to replace 10 with 100
        System.out.println("The Object that is replaced is: "
                           + absqlist.set(4, 100));

        // Displaying the modified linkedlist
        System.out.println("The new List is:" + absqlist);
    }
}
```

**Output:**

```
AbstractSequentialList:[50, 40, 30, 20, 10]
The Object that is replaced is: 40
The Object that is replaced is: 10
The new List is:[50, 400, 30, 20, 100]

```