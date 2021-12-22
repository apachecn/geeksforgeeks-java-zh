# Java 中的 CopyOnWriteArrayList subList()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-sublist-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-sublist-method-in-java-with-examples/)

类的 **subList()** 方法用于返回列表中指定的 fromIndex(包含)和 toIndex(不包含)之间的部分的视图。(如果 fromIndex 和 toIndex 相等，则返回的列表为空。)

返回的列表由该列表支持，因此返回列表中的非结构性变化反映在该列表中，反之亦然。返回的列表支持所有可选的列表操作。

**语法:**

```java
public List subList(int fromIndex, int toIndex)
```

**参数:**该方法将以下参数作为参数。

*   **从索引–**子列表的低端点(含)
*   **到索引–**子列表的高端点(不包括)

**返回值:**该方法返回列表中指定范围的**视图。**

**异常:**如果端点索引值超出范围(从索引大小开始)，此方法将抛出**索引**

下面是说明*子列表()*方法的例子。

**例 1:**

```java
// Java program to demonstrate
// subList() method
// for String value

import java.util.*;
import java.util.concurrent.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of CopyOnWriteArrayList<Integer>
            CopyOnWriteArrayList<String>
                arrlist = new CopyOnWriteArrayList<String>();

            // Populating arrlist1
            arrlist.add("A");
            arrlist.add("B");
            arrlist.add("C");
            arrlist.add("D");
            arrlist.add("E");

            // print arrlist
            System.out.println("Original arrlist: "
                               + arrlist);

            // getting the subList
            // using subList() method
            List<String> arrlist2 = arrlist.subList(2, 4);

            // print the subList
            System.out.println("Sublist of arrlist: "
                               + arrlist2);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
Original arrlist: [A, B, C, D, E]
Sublist of arrlist: [C, D]

```

**示例 2:** 适用于*指数出界异常*

```java
// Java program to demonstrate
// subList() method
// for IndexOutOfBoundsException

import java.util.*;
import java.util.concurrent.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // Creating object of CopyOnWriteArrayList<Integer>
            CopyOnWriteArrayList<String>
                arrlist = new CopyOnWriteArrayList<String>();

            // Populating arrlist1
            arrlist.add("A");
            arrlist.add("B");
            arrlist.add("C");
            arrlist.add("D");
            arrlist.add("E");

            // print arrlist
            System.out.println("Original arrlist: "
                               + arrlist);

            // getting the subList
            // using subList() method
            System.out.println("\nEnd index value is out of range");
            List<String> arrlist2 = arrlist.subList(2, 7);

            // print the subList
            System.out.println("Sublist of arrlist: "
                               + arrlist2);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
Original arrlist: [A, B, C, D, E]

End index value is out of range
Exception thrown: java.lang.IndexOutOfBoundsException

```