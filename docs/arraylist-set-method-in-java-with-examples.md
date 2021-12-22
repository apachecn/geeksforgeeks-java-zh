# Java 中的数组列表集()方法，示例

> 原文:[https://www . geesforgeks . org/ArrayList-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/arraylist-set-method-in-java-with-examples/)

使用**[Java . util . arraylis](https://www.geeksforgeeks.org/arraylist-in-java/)t**类的 **set()** 方法将列表中指定位置的元素替换为指定元素。

**语法:**

```java
public E set(int index, E element)
```

**参数:**该方法将以下参数作为参数。

*   **索引-** 要替换的元素的索引
*   **元素-** 要存储在指定位置的元素

**返回值:**该方法返回先前在指定位置的**元素**。

**异常:**如果索引不在数组列表的大小范围内，该方法抛出**indexout of boundsexception**。

下面是举例说明 *set()* 方法。

**例 1:**

```java
// Java program to demonstrate
// set() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Creating object of ArrayList<Integer>
            ArrayList<Integer>
                arrlist = new ArrayList<Integer>();

            // Populating arrlist1
            arrlist.add(1);
            arrlist.add(2);
            arrlist.add(3);
            arrlist.add(4);
            arrlist.add(5);

            // print arrlist
            System.out.println("Before operation: "
                               + arrlist);

            // Replacing element at the index 3 with 30
            // using method set()
            int i = arrlist.set(3, 30);

            // Print the modified arrlist
            System.out.println("After operation: "
                               + arrlist);

            // Print the Replaced element
            System.out.println("Replaced element: "
                               + i);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:**

```java
Before operation : [1, 2, 3, 4, 5]
After operation : [1, 2, 3, 30, 5]
Replaced element : 4

```

**示例 2:** 适用于*指数出界异常*

```java
// Java program to demonstrate
// set() method
// for IndexOutOfBoundsException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Creating object of ArrayList<Integer>
            ArrayList<Integer>
                arrlist = new ArrayList<Integer>();

            // Populating arrlist1
            arrlist.add(1);
            arrlist.add(2);
            arrlist.add(3);
            arrlist.add(4);
            arrlist.add(5);

            // print arrlist
            System.out.println("Before operation : "
                               + arrlist);

            // Replacing element at the index 7 with 30
            // using method set()
            System.out.println("\nTrying to Replace"
                               + " the element at"
                               + " (index > Capacity) ");
            int i = arrlist.set(7, 30);

            // Print the modified arrlist
            System.out.println("After operation: "
                               + arrlist);

            // Print the Replaced element
            System.out.println("Replaced element: "
                               + i);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Before operation : [1, 2, 3, 4, 5]

Trying to Replace the element at (index > Capacity) 
Exception thrown : java.lang.IndexOutOfBoundsException: Index: 7, Size: 5

```