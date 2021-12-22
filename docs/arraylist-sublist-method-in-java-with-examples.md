# Java 中的 ArrayList subList()方法，带示例

> 原文:[https://www . geesforgeks . org/ArrayList-sublist-method-in-Java-with-examples/](https://www.geeksforgeeks.org/arraylist-sublist-method-in-java-with-examples/)

**[Java . util . ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/)**类的 **subList()** 方法用于返回此列表中指定的 fromIndex(包含)和 toIndex(不包含)之间的部分的视图。(如果 fromIndex 和 toIndex 相等，则返回的列表为空。)

返回的列表由该列表支持，因此返回列表中的非结构性变化反映在该列表中，反之亦然。返回的列表支持所有可选的列表操作。

**语法:**

```
public List subList(int fromIndex, int toIndex)
```

**参数:**该方法将以下参数作为参数。

*   **从索引–**子列表的低端点(含)
*   **到索引–**子列表的高端点(不包括)

**返回值:**该方法返回列表中指定范围的**视图。**

**异常:**该方法抛出如下异常。

*   如果端点索引值超出范围(从索引大小开始)，则**indexout of BoundSexception–**
*   **如果端点索引出现故障，则出现 IllegalArgumentException–**(从索引>到索引)

下面是说明*子列表()*方法的例子。

**例 1:**

```
// Java program to demonstrate
// subList() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of ArrayList<Integer>
            ArrayList<String>
                arrlist = new ArrayList<String>();

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
            System.out.println("Exception thrown : " + e);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Original arrlist: [A, B, C, D, E]
Sublist of arrlist: [C, D]

```

**示例 2:** 适用于*指数出界异常*

```
// Java program to demonstrate
// subList() method
// for IndexOutOfBoundsException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // Creating object of ArrayList<Integer>
            ArrayList<String>
                arrlist = new ArrayList<String>();

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
            System.out.println("Exception thrown : " + e);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Original arrlist: [A, B, C, D, E]

End index value is out of range
Exception thrown : java.lang.IndexOutOfBoundsException: toIndex = 7

```

**示例 3:** 适用于*非法文档异常*

```
// Java program to demonstrate
// subList() method
// for IllegalArgumentException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Creating object of ArrayList<Integer>
            ArrayList<String>
                arrlist = new ArrayList<String>();

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
            System.out.println("\nEndpoint indices "
                               + "are out of order"
                               + " (fromIndex > toIndex)");
            List<String> arrlist2 = arrlist.subList(7, 2);

            // print the subList
            System.out.println("Sublist of arrlist: "
                               + arrlist2);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown: " + e);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```
Original arrlist: [A, B, C, D, E]

Endpoint indices are out of order (fromIndex > toIndex)
Exception thrown: java.lang.IllegalArgumentException: fromIndex(7) > toIndex(2)

```