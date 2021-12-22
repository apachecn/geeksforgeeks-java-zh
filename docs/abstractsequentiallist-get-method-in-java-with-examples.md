# Java 中的抽象顺序列表 get()方法，示例

> 原文:[https://www . geesforgeks . org/abstractsequentialist-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractsequentiallist-get-method-in-java-with-examples/)

[](https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/)**的 **get()** 方法用于从抽象顺序列表中获取或检索特定索引处的元素。**

****语法:****

```
AbstractSequentialList.get(int index)
```

****参数:**参数*索引*是整数数据类型，指定要从抽象顺序列表中提取的元素的位置或索引。**

****返回值:**该方法返回出现在参数*索引*指定位置的元素。**

**下面的程序说明了 Java . util . abstractsequentialist . get()方法:**

****例 1:****

```
// Java code to illustrate get() method

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

        // Displaying the list
        System.out.println("AbstractSequentialList:"
                           + absqlist);

        // Fetching the specific element from the list
        System.out.println("The element is: "
                           + absqlist.get(2));
    }
}
```

****Output:**

```
AbstractSequentialList:[Geeks, for, Geeks, 10, 20]
The element is: Geeks

```** 

****例 2:****

```
// Java code to illustrate get() method

import java.util.*;
import java.util.AbstractSequentialList;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractSequentialList
        AbstractSequentialList<Integer>
            absqlist = new LinkedList<Integer>();

        // Use add() method to add elements
        absqlist.add(1);
        absqlist.add(2);
        absqlist.add(3);
        absqlist.add(4);
        absqlist.add(5);

        // Displaying the list
        System.out.println("AbstractSequentialList:"
                           + absqlist);

        // Fetching the specific element from the list
        System.out.println("The element is: "
                           + absqlist.get(4));
    }
}
```

****Output:**

```
AbstractSequentialList:[1, 2, 3, 4, 5]
The element is: 5

```**