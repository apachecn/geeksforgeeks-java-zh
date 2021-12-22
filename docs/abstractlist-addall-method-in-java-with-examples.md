# Java 中的抽象列表 addAll()方法，示例

> 原文:[https://www . geesforgeks . org/abstract list-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-addall-method-in-java-with-examples/)

**[Java . util . abstract list](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的 **addAll()** 方法用于将指定集合中的所有元素插入到该列表的指定位置。

*   这会将当前在该位置的元素(如果有)和任何后续元素向右移动(增加它们的索引)。
*   新元素将按照指定集合的迭代器返回的顺序出现在列表中。
*   如果在操作过程中修改了指定的集合，则此操作的行为是未定义的。

此实现获取指定集合的迭代器并对其进行迭代，使用 add(int，E)将从迭代器获得的元素插入列表的适当位置，一次一个。为了提高效率，许多实现会覆盖此方法。

**语法:**

```
public boolean addAll(int index, Collection c)
```

**参数:**该方法将以下参数作为参数。

*   **索引-** 插入指定集合中第一个元素的索引
*   **c-** 包含要添加到此列表中的元素的集合
*   **返回值:**如果该列表因调用而改变，则该方法返回**真**。

*   **异常:**该方法抛出如下异常。
    *   **null pointerexception–**如果指定的集合包含一个或多个 null 元素，并且此列表不允许 null 元素，或者如果指定的集合为 null
    *   **IndexOutOfBoundsException–**如果索引超出范围(索引大小())。

下面是举例说明 **addAll()** 方法。

**例 1:**

```
// Java program to demonstrate
// addAll() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of AbstractList<String>
            AbstractList<String>
                arrlist1 = new ArrayList<String>();

            // Populating arrlist1
            arrlist1.add("A");
            arrlist1.add("B");
            arrlist1.add("C");
            arrlist1.add("D");
            arrlist1.add("E");

            // print arrlist1
            System.out.println("Original ArrayListlist : "
                               + arrlist1);

            // Creating another object of AbstractList<String>
            AbstractList<String>
                arrlist2 = new ArrayList<String>();

            // Populating arrlist2
            arrlist2.add("X");
            arrlist2.add("Y");
            arrlist2.add("Z");

            // print arrlist2
            System.out.println("ArrayList elements "
                               + "to be added : "
                               + arrlist2);

            // adding the specified element
            // starting from index 2
            // using addAll() method
            boolean value = arrlist1.addAll(2, arrlist2);

            // print the value
            System.out.println("Operation successful : "
                               + value);

            // print the new arrlist
            System.out.println("New ArrayList : "
                               + arrlist1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Original ArrayListlist : [A, B, C, D, E]
ArrayList elements to be added : [X, Y, Z]
Operation successful : true
New ArrayList : [A, B, X, Y, Z, C, D, E]

```

**示例 2:** 适用于*空指针异常*

```
// Java program to demonstrate
// addAll() method
// for NullPointerException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Creating object of AbstractList<String>
            AbstractList<String>
                arrlist1 = new ArrayList<String>();

            // Populating arrlist1
            arrlist1.add("A");
            arrlist1.add("B");
            arrlist1.add("C");
            arrlist1.add("D");
            arrlist1.add("E");

            // print arrlist1
            System.out.println("Original ArrayListlist : "
                               + arrlist1);

            // Creating another object of AbstractList<String>
            AbstractList<String> arrlist2 = null;

            // printing the arrlist2
            System.out.println("ArrayList to be added : "
                               + arrlist2);

            // adding the specified element
            // starting from index 2
            // using addAll() method
            System.out.println("\nTrying to get"
                               + " the null collection");
            boolean value = arrlist1.addAll(2, arrlist2);

            // print the value
            System.out.println("operation successful : "
                               + value);

            // print the new arrlist
            System.out.println("New ArrayList : "
                               + arrlist1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Original ArrayListlist : [A, B, C, D, E]
ArrayList to be added : null

Trying to get the null collection
Exception thrown : java.lang.NullPointerException

```

**示例 3:** 适用于*指数出界异常*

```
// Java program to demonstrate
// addAll() method
// for IndexOutOfBoundsException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of AbstractList<String>
            AbstractList<String>
                arrlist1 = new ArrayList<String>();

            // Populating arrlist1
            arrlist1.add("A");
            arrlist1.add("B");
            arrlist1.add("C");
            arrlist1.add("D");
            arrlist1.add("E");

            // print arrlist1
            System.out.println("Original ArrayListlist : "
                               + arrlist1);

            // Creating another object of AbstractList<String>
            AbstractList<String>
                arrlist2 = new ArrayList<String>();

            // Populating arrlist2
            arrlist2.add("X");
            arrlist2.add("Y");
            arrlist2.add("Z");

            // print arrlist2
            System.out.println("ArrayList elements to be added : "
                               + arrlist2);

            // adding the specified element
            // starting from index 2
            // using addAll() method
            System.out.println("\nTrying to put the out"
                               + " of range index ");
            boolean value = arrlist1.addAll(-1, arrlist2);

            // print the value
            System.out.println("operation succecfull : "
                               + value);

            // print the new arrlist
            System.out.println("New ArrayList : " + arrlist1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Original ArrayListlist : [A, B, C, D, E]
ArrayList elements to be added : [X, Y, Z]

Trying to put the out of range index 
Exception thrown : java.lang.IndexOutOfBoundsException: Index: -1, Size: 5

```