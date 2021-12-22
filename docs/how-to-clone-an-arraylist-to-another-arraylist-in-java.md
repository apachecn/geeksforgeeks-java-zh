# 如何在 Java 中将一个 ArrayList 克隆到另一个 ArrayList？

> 原文:[https://www . geesforgeks . org/如何在 java 中将一个数组列表克隆到另一个数组列表/](https://www.geeksforgeeks.org/how-to-clone-an-arraylist-to-another-arraylist-in-java/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)类的 [clone()](https://www.geeksforgeeks.org/arraylist-clone-method-in-java-with-examples/) 方法用于将一个数组列表克隆到 Java 中的另一个数组列表，因为它返回其调用方数组列表的一个浅层副本。

**语法:**

> 公共对象克隆()；

**返回值:**该函数返回对象实例的副本。

下面的程序说明了 Java.util.ArrayList.clone()方法:

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to clone an ArrayList to another ArrayList

import java.util.ArrayList;
public class GFG {

    public static void main(String a[])
    {

        // create ArrayList
        ArrayList<String> ArrList1
            = new ArrayList<String>();

        // Insert elements in ArrayList
        ArrList1.add("Mukul");
        ArrList1.add("Rahul");
        ArrList1.add("Suraj");
        ArrList1.add("Mayank");

        // print ArrayList1
        System.out.println("Original ArrayList = "
                           + ArrList1);

        // clone ArrayList
        ArrayList ArrList2
            = (ArrayList)ArrList1.clone();

        // print ArrayList2
        System.out.println("Clone ArrayList2 = "
                           + ArrList2);
    }
}
```

**Output**

```java
Original ArrayList = [Mukul, Rahul, Suraj, Mayank]
Clone ArrayList2 = [Mukul, Rahul, Suraj, Mayank]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate clone() method

import java.io.*;
import java.util.*;

public class ArrayListDemo {

    public static void main(String args[])
    {

        // Creating an empty ArrayList
        ArrayList<Integer> list = new ArrayList<Integer>();

        // Use add() method
        // to add elements in the list
        list.add(16);
        list.add(32);
        list.add(48);

        // Displaying the list
        System.out.println("First ArrayList: " + list);

        // Creating another linked list and copying
        // creates a shallow copy
        ArrayList<Integer> sec_list
            = (ArrayList<Integer>)list.clone();

        sec_list.add(64);

        // Displaying the list
        System.out.println("First ArrayList: " + list);

        // Displaying the other linked list
        System.out.println("Second ArrayList is: "
                           + sec_list);
    }
}
```

**输出**

```java
First ArrayList: [16, 32, 48]
First ArrayList: [16, 32, 48]
Second ArrayList is: [16, 32, 48, 64]
```