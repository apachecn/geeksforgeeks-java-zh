# Java 中的抽象列表 lastIndexOf()方法，示例

> 原文:[https://www . geesforgeks . org/abstract list-last indexof-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-lastindexof-method-in-java-with-examples/)

**[Java . util . abstract list](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的 **lastIndexOf()** 方法用于返回该列表中指定元素最后一次出现的索引，如果该列表不包含该元素，则返回-1。更正式地说，返回最高索引 I，这样(o==null？get(i)==null : o.equals(get(i))，如果没有这样的索引，则为-1。

**语法:**

```
public int lastIndexOf(Object o)
```

**参数:**该方法以的**对象为参数，是要搜索的元素。**

**返回值:**该方法返回该列表中指定元素最后一次出现的**索引，如果该列表不包含该元素，则返回-1。**

**异常:**如果指定的元素为空并且该列表不允许空元素，则该方法抛出**空指针异常**。

以下是说明 *lastIndexOf()* 方法的例子。

**例 1:**

```
// Java program to demonstrate
// lastIndexOf() method
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
            arrlist1.add("A");
            arrlist1.add("B");
            arrlist1.add("E");

            // print arrlist1
            System.out.println("ArrayList : "
                               + arrlist1);

            // getting the index of last occurrence
            // using lastIndexOf() method
            int lastindex = arrlist1.lastIndexOf("A");

            // printing the Index
            System.out.println("Last index of A : "
                               + lastindex);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayList : [A, B, A, B, E]
Last index of A : 2

```

**例 2:**

```
// Java program to demonstrate
// lastIndexOf() method
// for NullPointerException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of AbstractList<String>
            AbstractList<String> arrlist1 = null;

            // print arrlist1
            System.out.println("ArrayList : "
                               + arrlist1);

            // getting the index of last occurrence
            // using lastIndexOf() method
            System.out.println("\nTrying to get"
                               + " the index from"
                               + " null ArrayList");
            int lastindex = arrlist1.lastIndexOf("B");

            // printing the Index
            System.out.println("Last index of B : "
                               + lastindex);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayList : null

Trying to get the index from null ArrayList
Exception thrown : java.lang.NullPointerException

```