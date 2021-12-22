# Java 中的抽象列表 get()方法，示例

> 原文:[https://www . geesforgeks . org/abstract list-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-get-method-in-java-with-examples/)

**[Java . util . abstract list](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的 **get()** 方法用于返回该列表中指定位置的元素。

**语法:**

```
public abstract E get(int index)
```

**参数:**该方法以元素的**索引**为参数，返回的元素。

**返回值:**该方法返回列表中指定位置的**元素**。

**异常:**如果索引超出范围(index = size())，该方法抛出**indexout of boundsexception**。

下面举例说明 *get()* 方法。

**例 1:**

```
// Java program to demonstrate
// get() method
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

            // getting the value at the index 3
            // using get() method
            int value = arrlist1.get(3);

            // print the value
            System.out.println("Element at index 3 : "
                               + value);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayListlist : [10, 20, 30, 40, 50]
Element at index 3 : 40

```

**例 2:**

```
// Java program to demonstrate
// get() method
// for IndexOutOfBoundsException

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

            // getting the value at the index 7
            // using get() method
            System.out.println("\nTrying to get "
                               + "the element from out"
                               + " of range index ");
            int value = arrlist1.get(7);

            // print the value
            System.out.println("Element at index 7 : "
                               + value);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayListlist : [10, 20, 30, 40, 50]

Trying to get the element from out of range index 
Exception thrown : java.lang.IndexOutOfBoundsException: Index: 7, Size: 5

```