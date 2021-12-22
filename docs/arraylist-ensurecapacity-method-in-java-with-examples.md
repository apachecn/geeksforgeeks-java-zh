# Java 中的 ArrayList ensureCapacity()方法，带示例

> 原文:[https://www . geesforgeks . org/ArrayList-ensurecapacity-method-in-Java-with-examples/](https://www.geeksforgeeks.org/arraylist-ensurecapacity-method-in-java-with-examples/)

[**Java . util . ArrayList**](https://www.geeksforgeeks.org/arraylist-in-java/)类的 **ensureCapacity()** 方法增加了这个 ArrayList 实例的容量，如果需要的话，确保它至少可以容纳最小容量参数指定的元素数量。

**语法:**

```
public void ensureCapacity(int minCapacity)
```

**参数:**该方法以**期望最小容量**为参数。

以下是说明**保证能力()**方法的例子。

**例 1:**

```
// Java program to demonstrate
// ensureCapacity() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of ArrayList<Integer>
            ArrayList<Integer>
                arrlist = new ArrayList<Integer>();

            // adding element to arrlist
            arrlist.add(10);
            arrlist.add(20);
            arrlist.add(30);
            arrlist.add(40);

            // Print the ArrayList
            System.out.println("ArrayList: "
                               + arrlist);

            // ensure that the ArrayList
            // can hold upto 5000 elements
            // using ensureCapacity() method
            arrlist.ensureCapacity(5000);

            // Print
            System.out.println("ArrayList can now"
                               + " surely store upto"
                               + " 5000 elements.");
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayList: [10, 20, 30, 40]
ArrayList can now surely store upto 5000 elements.

```

**例 2:**

```
// Java program to demonstrate
// ensureCapacity() method for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of ArrayList<Integer>
            ArrayList<String>
                arrlist = new ArrayList<String>();

            // adding element to arrlist
            arrlist.add("A");
            arrlist.add("B");
            arrlist.add("C");
            arrlist.add("D");

            // Print the ArrayList
            System.out.println("ArrayList: "
                               + arrlist);

            // ensure that the ArrayList
            // can hold upto 400 elements
            // using ensureCapacity() method
            arrlist.ensureCapacity(400);

            // Print
            System.out.println("ArrayList can now"
                               + " surely store upto"
                               + " 400 elements.");
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayList: [A, B, C, D]
ArrayList can now surely store upto 400 elements.

```