# Java 中的抽象列表迭代器()方法，示例

> 原文:[https://www . geesforgeks . org/abstract list-iterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-iterator-method-in-java-with-examples/)

**[Java . util . abstract list](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的**迭代器()**方法用于以适当的顺序返回该列表中元素的迭代器。

这个实现返回迭代器接口的简单实现，依赖于支持列表的 size()，get(int)和 remove(int)方法。

**语法:**

```java
public Iterator iterator()
```

**返回值:**这个方法返回一个**迭代器**，以适当的顺序遍历列表中的元素。

下面是说明*迭代器()*方法的例子。

**例 1:**

```java
// Java program to demonstrate
// iterator() method
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
            System.out.println("ArrayList : "
                               + arrlist1);

            // creating object of Iterator
            // using iterator() method
            Iterator it = arrlist1.iterator();

            // printing the iterated value
            while (it.hasNext()) {
                System.out.println("Value is : "
                                   + it.next());
            }
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
ArrayList : [10, 20, 30, 40, 50]
Value is : 10
Value is : 20
Value is : 30
Value is : 40
Value is : 50

```

**例 2:**

```java
// Java program to demonstrate
// iterator() method
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
            System.out.println("ArrayList : "
                               + arrlist1);

            // creating object of Iterator
            // using iterator() method
            Iterator it = arrlist1.iterator();

            // printing the iterated value
            while (it.hasNext()) {
                System.out.println("Value is : "
                                   + it.next());
            }
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
ArrayList : [A, B, C, D, E]
Value is : A
Value is : B
Value is : C
Value is : D
Value is : E

```