# Java 中的抽象列表索引()方法，示例

> 原文:[https://www . geesforgeks . org/abstract list-indexof-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-indexof-method-in-java-with-examples/)

**[Java . util . abstract list](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的 **indexOf()** 方法用于返回该列表中指定元素第一次出现的索引，如果该列表不包含该元素，则返回-1。更正式地说，返回最低的索引 I，这样(o==null？get(i)==null : o.equals(get(i))，如果没有这样的索引，则为-1。

**语法:**

```
public int indexOf(Object o)
```

**参数:**该方法以的**对象为参数，该参数是要搜索的元素。**

**返回值:**该方法返回该列表中指定元素第一次出现的**索引**，如果该列表不包含该元素，则返回-1。

下面是举例说明方法的**索引。**

**例 1:**

```
// Java program to demonstrate
// indexOf() method
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
            System.out.println("ArrayListlist : "
                               + arrlist1);

            // getting the index of element 30
            // using indexOf() method
            int index = arrlist1.indexOf(30);

            // print the index
            System.out.println("index : " + index);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayListlist : [10, 20, 30, 40, 50]
index : 2

```

**例 2:**

```
// Java program to demonstrate
// indexOf() method
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
            System.out.println("ArrayListlist : "
                               + arrlist1);

            // getting the index of element 25
            // using indexOf() method
            int index = arrlist1.indexOf(25);

            // print the index
            System.out.println("Index of 25 : "
                               + index);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayListlist : [10, 20, 30, 40, 50]
Index of 25 : -1

```

**示例 3:** 为空值

```
// Java program to demonstrate
// indexOf() method
// for null value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
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
            System.out.println("ArrayListlist : "
                               + arrlist1);

            // creating null object
            Object value = null;

            // getting the index of element null
            // using indexOf() method
            int index = arrlist1.indexOf(value);

            // print the index
            System.out.println("Index of null : "
                               + index);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayListlist : [10, 20, 30, 40, 50]
Index of null : -1

```