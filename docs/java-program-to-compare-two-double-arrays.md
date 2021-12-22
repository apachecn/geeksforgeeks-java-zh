# 比较两个双数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序对双双数组进行比较/](https://www.geeksforgeeks.org/java-program-to-compare-two-double-arrays/)

Java 双数组仅用于存储双数据类型值。双数组中元素的默认值为 0。

**我们可以通过两种方式比较两个双数组:**

1.  Naive methods of traversing the whole array and comparing each element.
2.  通过 [Arrays.equals()](https://www.geeksforgeeks.org/java-util-arrays-equals-java-examples/) 方法。

**方法 1:天真的方法**

*   Traverse two arrays by using the for loop, comparing one element at a time.

## Java

```java
// Java program to compare two double arrays

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {

    public static void main(String[] args) throws java.lang.Exception
    {    
        // Two double arrays array1 and array2
        double[] array1 = { 1.5, 2.5, 3.5, 4.5 };
        double[] array2 = { 1.5, 2.5, 3.5 };

        // when the length of two arrays are not 
        // same, then both the arrays cannot be equal
        // so no need of comparing each element
        if (array1.length != array2.length)

            System.out.println("Arrays are not Equal");

        else {
            for (int i = 0; i < array1.length; i++)
            {   
                // comparing each and every element
                if (array1[i] != array2[i])
                {
                    System.out.println("Arrays are not Equal");
                    System.exit(0);
                }
            }

            System.out.println("Arrays are Equal");
        }
    }
}
```

**输出**

```java
Arrays are not Equal
```