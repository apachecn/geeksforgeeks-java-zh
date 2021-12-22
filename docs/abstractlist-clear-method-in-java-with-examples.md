# 用示例在 Java 中抽象出 clear()方法

> 原文:[https://www . geesforgeks . org/abstract list-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-clear-method-in-java-with-examples/)

**java.util.AbstractList** 类的 **clear()** 方法用于从该列表中移除所有元素。该呼叫返回后，列表将为空。

**语法:**

```
public void clear()
```

**返回值:**这个方法不返回任何东西。

下面举例说明 *clear()* 方法。

**例 1:**

```
// Java program to demonstrate
// clear() method
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

            // print the ArrayList
            System.out.println("Original ArrayListlist : "
                               + arrlist1);

            // Removing all the elements
            // using clear() method
            arrlist1.clear();

            // print the new ArrayList
            System.out.println("New ArrayList : "
                               + arrlist1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**Output:**

```
Original ArrayListlist : [A, B, C, D, E]
New ArrayList : []

```

**例 2:**

```
// Java program to demonstrate
// clear() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of AbstractList<Integer>
            AbstractList<Integer>
                arrlist1 = new ArrayList<Integer>();

            // Populating arrlist1
            arrlist1.add(10);
            arrlist1.add(20);
            arrlist1.add(30);
            arrlist1.add(40);
            arrlist1.add(50);

            // print the ArrayList
            System.out.println("Original ArrayListlist : "
                               + arrlist1);

            // Removing all the elements
            // using clear() method
            arrlist1.clear();

            // print the new ArrayList
            System.out.println("New ArrayList : "
                               + arrlist1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Original ArrayListlist : [10, 20, 30, 40, 50]
New ArrayList : []

```