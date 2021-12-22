# 寻找 Java 向量的最大元素

> 原文:[https://www . geeksforgeeks . org/finding-最大元素-of-java-vector/](https://www.geeksforgeeks.org/finding-maximum-element-of-java-vector/)

[Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 实现了一个动态数组，这意味着它可以根据需要增长或收缩。像数组一样，它包含可以使用整数索引访问的组件。我们知道两种声明数组的方法，即要么使用固定大小的数组，要么根据用户的需求根据内存中分配的数组输入大小。

```java
int Array_name[Fixed_size] ;

int array_name[variable_size] ;
```

在这两种方式中，我们都会浪费内存，因此，为了正确利用内存优化，引入了**向量**。我们必须找出给定 Java 向量中的最大元素。

**例:**

```java
Input***:*** [1,2,3,4,5]
Output***:*** 5
Input***:*** [88,23,76,90,56]
Output***:*** 90
```

**方法 1:使用预定义功能**

*   为了找到给定向量的最小元素，我们使用[Java . util . collections . max()](https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/)方法。
*   这将直接找到向量中的最大值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find
// maximum element in java vector

import java.io.*;
import java.util.Collections;
import java.util.Vector;
public class GFG {

    public static void main(String args[])

        Vector<Integer> vec = new Vector<Integer>();

        vec.add(1);
        vec.add(2);
        vec.add(3);
        vec.add(4);
        vec.add(5);

        System.out.println("Vector elements: " + vec);

        System.out.println("The maximum element of the Vector is: "
         + Collections.max(vec));
    }
 }
```

**Output**

```java
Vector elements: [1, 2, 3, 4, 5]
The maximum element of the Vector is: 5
```

**最坏情况时间复杂度:O(n)** 其中 n 是向量中存在的元素个数。

**方法 2:比较向量**

*   First, we will initialize a vector, such as v, and then we will store the value in the vector.
*   Next, we will take a variable and let **u** s say maxNumber and assign it to the maximum possible value.
*   Traverse to the end of the vector and compare each element of the vector with maxNumber.
*   If the elements in the vector are larger than maxNumber, update maxNumber to this value.
*   Maximum number of prints.

## Java

```java
// Java program to find largest element
// present in Vector via comparison

import java.io.*;

// Importing Vector Class 
import java.util.Vector;

// Importing Iterator Class
import java.util.Iterator;

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

        // Assigning min value possible
        int maxValue = Integer.MIN_VALUE;

        // Creating an iterator to traverse through vector
        // in the beginning itr will point to index just
        // before first element
        Iterator itr = v.iterator();

        // See if there is any next element
        while (itr.hasNext()) 
        {
            // Moving iterator to next element
            int element = (Integer)itr.next();

            // Comparing if element is larger than maxValue
            if (element > maxValue) 
            {
                // Update maxValue
                maxValue = element;
            }
        }

        // Print maxVaue
        System.out.println( "The largest element present in Vector is : "
            + maxValue);
    }
}
```

**输出**

```java
The largest element present in Vector is : 50
```

**时间复杂度:O(n)** 其中 n 是向量中存在的元素个数。