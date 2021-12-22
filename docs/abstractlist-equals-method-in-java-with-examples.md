# Java 中的抽象列表等于()方法，示例

> 原文:[https://www . geesforgeks . org/abstract list-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-equals-method-in-java-with-examples/)

**[Java . util . abstract list](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的 **equals()** 方法用于将指定对象与该列表进行相等比较。当且仅当指定的对象也是一个列表，两个列表具有相同的大小，并且两个列表中所有对应的元素对相等时，返回 true。(两个元素 e1 和 e2 相等，如果(e1==null？e2==null : e1.equals(e2))。)换句话说，如果两个列表以相同的顺序包含相同的元素，则它们被定义为相等。

**语法:**

```
public boolean equals(Object o)
```

**参数:**该方法将的**对象作为参数与该列表进行相等比较。**

**返回值:**如果指定的对象等于这个列表，这个方法返回**真**。

以下是说明**等于()**方法的例子。

**例 1:**

```
// Java program to demonstrate
// equals() method
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
            System.out.println("First ArrayListlist : "
                               + arrlist1);

            // Creating another object of AbstractList<String>
            AbstractList<String>
                arrlist2 = new ArrayList<String>();

            // Populating arrlist2
            arrlist2.add("A");
            arrlist2.add("B");
            arrlist2.add("C");
            arrlist2.add("D");
            arrlist2.add("E");

            // print arrlist2
            System.out.println("Second ArrayList : "
                               + arrlist2);

            // comparing first ArrayList to another
            // using equals() method
            boolean value = arrlist1.equals(arrlist2);

            // print the value
            System.out.println("Are both list equal : "
                               + value);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
First ArrayListlist : [A, B, C, D, E]
Second ArrayList : [A, B, C, D, E]
Are both list equal : true

```

**例 2:**

```
// Java program to demonstrate
// equals() method
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

            // print arrlist1
            System.out.println("First ArrayListlist : "
                               + arrlist1);

            // Creating another object of AbstractList<Integer>
            AbstractList<Integer>
                arrlist2 = new ArrayList<Integer>();

            // Populating arrlist2
            arrlist2.add(10);
            arrlist2.add(20);
            arrlist2.add(30);

            // print arrlist2
            System.out.println("Second ArrayList : "
                               + arrlist2);

            // comparing first ArrayList to another
            // using equals() method
            boolean value = arrlist1.equals(arrlist2);

            // print the value
            System.out.println("Are both list equal : "
                               + value);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
First ArrayListlist : [10, 20, 30, 40, 50]
Second ArrayList : [10, 20, 30]
Are both list equal : false

```