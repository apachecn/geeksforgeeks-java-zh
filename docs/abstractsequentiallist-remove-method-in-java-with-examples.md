# Java 中的抽象顺序列表移除()方法，示例

> 原文:[https://www . geesforgeks . org/abstractsequentialist-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractsequentiallist-remove-method-in-java-with-examples/)

[**【抽象顺序列表】**](https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/) 的**移除(int index)** 方法用于从特定位置或索引移除抽象顺序列表中的元素。

**语法:**

```
AbstractSequentialList.remove(int index)
```

**参数:**参数*索引*是整数数据类型，指定要从抽象顺序列表中删除的元素的位置。

**返回值:**该方法返回刚从列表中删除的元素。

下面的程序说明了 abstractsequentialist . remove(int index)方法:

**程序 1:**

```
// Java code to illustrate remove() method

import java.util.*;
import java.util.AbstractSequentialList;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String>
            absqlist = new LinkedList<String>();

        // Using add() method to add elements in the list
        absqlist.add("Geeks");
        absqlist.add("for");
        absqlist.add("Geeks");
        absqlist.add("10");
        absqlist.add("20");

        // Output the list
        System.out.println("AbstractSequentialList: "
                           + absqlist);

        // Remove the head using remove()
        absqlist.remove(3);

        // Print the final list
        System.out.println("Final List: "
                           + absqlist);
    }
}
```

**Output:**

```
AbstractSequentialList: [Geeks, for, Geeks, 10, 20]
Final List: [Geeks, for, Geeks, 20]

```

**程序 2:**

```
// Java code to illustrate remove()
// with position of element passed as parameter

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

        // Output the list
        System.out.println("AbstractSequentialList:"
                           + absqlist);

        // Remove the head using remove()
        absqlist.remove(0);

        // Print the final list
        System.out.println("Final AbstractSequentialList:"
                           + absqlist);
    }
}
```

**Output:**

```
AbstractSequentialList:[Geeks, for, Geeks, 10, 20]
Final AbstractSequentialList:[for, Geeks, 10, 20]

```