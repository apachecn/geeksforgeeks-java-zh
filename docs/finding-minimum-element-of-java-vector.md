# 寻找 Java 向量的最小元素

> 原文:[https://www . geeksforgeeks . org/finding-minimum-of-Java-vector/](https://www.geeksforgeeks.org/finding-minimum-element-of-java-vector/)

[Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 实现了一个动态数组，这意味着它可以根据需要增长或收缩。像数组一样，它包含可以使用整数索引访问的组件。我们知道两种声明数组的方法，即要么使用固定大小的数组，要么根据用户的需求根据内存中分配的数组输入大小。

```java
int Array_name[Fixed_size] ;

int array_name[variable_size] ;
```

在这两种方式中，我们都会浪费内存，因此，为了正确利用内存优化，引入了**向量**。

我们需要找出给定 java 向量中的**最小元素**。

**示例:**

```java
***Input:*** [1,2,3,4,5]
***Output:*** 1

***Input:*** [88,23,76,90,56]
***Output:*** 23
```

**方法 1:使用预定义功能**

*   为了找到给定向量的最小元素，我们使用[Java . util . collections . min()](https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/)方法。
*   这直接找到向量中的最小值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find
// minimum element in java vector

import java.io.*;
import java.util.Collections;
import java.util.Vector;
public class GFG {

    public static void main(String args[])
    {

        Vector<Integer> vec = new Vector<Integer>();

        vec.add(1);
        vec.add(2);
        vec.add(3);
        vec.add(4);
        vec.add(5);

        System.out.println("Vector elements: " + vec);

        System.out.println("The maximum element of the Vector is: "
            + Collections.min(vec));
    }
}
```

**Output**

```java
Vector elements: [1, 2, 3, 4, 5]
The maximum element of the Vector is: 1
```

**最坏情况时间复杂度:O(n)** 其中 n 是向量中存在的元素个数。

**方法 2:比较向量中存在的每个元素**

*   首先，我们将初始化一个向量，比如 v，然后我们将值存储在这个向量中。
*   接下来，我们将取一个变量，让 **u** s 表示 minNumber，并分配可能的最小值。
*   遍历直到向量结束，并将向量的每个元素与最小数进行比较。
*   如果向量中的元素小于最小数，则将最小数更新为该值。
*   打印编号。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find minimum element
// present in Vector via comparison

import java.io.*;
// Importing Iterator Class
import java.util.Iterator;
// Importing Vector Class
import java.util.Vector;

class GFG {

    // Main Method
    public static void main(String[] args)
    {
        // initializing vector of Integer type
        Vector<Integer> v = new Vector<Integer>();

        // Adding elements in vector
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);

        // Assigning max value possible
        int minValue = Integer.MAX_VALUE;

        // Creating an iterator to traverse through vector
        // in the beginning itr will point to index just
        // before first element
        Iterator itr = v.iterator();

        // See if there is any next element
        while (itr.hasNext())
        {
            // Moving iterator to next element
            int element = (Integer)itr.next();

            // Comparing if element is smaller than minValue
            if (element < minValue) 
            {
                // Update maxValue
                minValue = element;
            }
        }

        // Print minVaue
        System.out.println("The smallest element present in Vector is : "
            + minValue);
    }
}
```

**Output**

```java
The smallest element present in Vector is : 10
```

**时间复杂度:O(n)** 其中 n 是向量中存在的元素个数。