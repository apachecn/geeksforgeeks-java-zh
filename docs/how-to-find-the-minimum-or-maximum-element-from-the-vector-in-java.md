# 如何在 Java 中从向量中找到最小或最大元素？

> 原文:[https://www . geesforgeks . org/如何从 java 矢量中找到最小或最大元素/](https://www.geeksforgeeks.org/how-to-find-the-minimum-or-maximum-element-from-the-vector-in-java/)

[**集合**](https://www.geeksforgeeks.org/collections-in-java-2/) 是 Java 提供的一个框架，它提供了一个存储一组对象的架构。Vector()就是这样一个集合。有许多方法可以找到向量中的最小和最大元素。下面讨论了这些方法:

**方法:**

1.  使用[*collection . min()*T3】和](https://www.geeksforgeeks.org/collections-min-method-in-java-with-examples/) [*收藏。max()*](https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/) 方法。
2.  Use the iterative vector element to set the minimum-maximum value.

**方法 1:使用 Collections.min()和 Collections.max()方法**

Collections 包提供了一种在集合中查找最小值和最大值的静态方法。这些方法是 Collections.max()和 Collections.min()。

*   Collections.max()查找最大元素
*   Collections.min()查找集合中的最小元素。

**示例**

## Java

```
// Java Program to Find minimum and maximum elements
// from a Vector

// Importing all classes of
// java.util package
import java.util.*;

// Class to find min and max
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating(defining) a  Vector
        Vector<Integer> V = new Vector<Integer>();

        // Add elements in Vector
        // Custom inouts
        V.add(1);
        V.add(2);
        V.add(3);
        V.add(4);
        V.add(5);

        // Printing all elements of vector
        System.out.println("Vector elements : " + V);
        // Using inbuilt function to

        // find minimum number
        // using Collection.min() method
        int minNumber = Collections.min(V);

        // find maximum number
        // using Collection.max() method
        int maxNumber = Collections.max(V);

        // Print max element of the vector
        System.out.println("Maximum Number in Vector is : "
                           + maxNumber);

        // Print min element of th vector
        System.out.println("Minimum Number in Vector is : "
                           + minNumber);
    }
}
```

**输出**

```
Vector elements : [1, 2, 3, 4, 5]
Maximum Number in Vector is : 5
Minimum Number in Vector is : 1
```

**方法 2:** 使用迭代向量元素设置最小值-最大值。

**进场:**

*   Take a variable and say minNumber, and initialize it to the maximum value before comparing and updating it.
*   Take a variable and say maxNumber, and then initialize it to the minimum value for comparison and update.
*   Traverse the Vector and compare each element with the above bivariate–
    *   最小数字
    *   最大数量
*   Update the value of minNumber if the number is less than minNumber.
*   Update the value of maxNumber if the value is greater than maxNumber.

**示例**

## Java

```
// Java Program to Find minimum and maximum elements
// from a Vector

// Importing all classes of
// java.util package
import java.util.*;
// Importing Integer Wrapper class for
// primitive data type
import java.lang.Integer;

// Clas
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Assign maximum value to minValue Variable
        int minValue = Integer.MAX_VALUE;

        // Assign minimum value to maxValue Variable
        int maxValue = Integer.MIN_VALUE;

        // Creating a Vector
        Vector<Integer> V = new Vector<Integer>();

        // Adding elements into Vector
        // Custom inputs
        V.add(100);
        V.add(30);
        V.add(7);
        V.add(24);
        V.add(13);

      System.out.println("Vector elements : "+V);
        // For-each loop to traverse through vector

        // If element is present in vector
        for (Integer i : V) {

            // if greater than maxValue, then update
            if (i > maxValue) {
                maxValue = i;
            }

            // if less than minValue, then update
            if (i < minValue) {
                minValue = i;
            }
        }

        // Print maximum element in the Vector
        System.out.println("Maximum Element in Vector : "
                           + maxValue);

        // Print minimum element in the vector
        System.out.println("Minimum Element in Vector : "
                           + minValue);
    }
}
```

**输出**

```
Vector elements : [100, 30, 7, 24, 13]
Maximum Element in Vector : 100
Minimum Element in Vector : 7
```