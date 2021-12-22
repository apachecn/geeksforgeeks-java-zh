# 寻找矩阵中最大元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-matrix 中的最大元素/](https://www.geeksforgeeks.org/java-program-to-find-the-maximum-element-in-a-matrix/)

给定一个 N 行 m 列 N × M 阶的多维 2D 矩阵，任务是找出给定矩阵中的最大元素。

插图:

```java
Input  : mat[][] = { {1,3,4,19}, {11,10,12,1}, {7,9,0,4,99} }
Output : 99
```

**方法:**

1.  迭代方法(天真方法)
2.  使用递归原理(更优的方法)

**方法 1:** 迭代法

方法很简单，逐个迭代矩阵的每个元素，将两个元素的最大值存储在 max 变量中，如下面程序中所用，并返回包含矩阵最大元素的 max 变量。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Find the Maximum Element in a Matrix

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Method 1
    // To find the maximum element
    static int max(int mat[][])
    {
        // Declaring and initializing varialble to unity
        // holding the maximum element value
        int max = 0;

        // Iterating over matrix
        // using nested for loops

        // Outer loop for rows
        for (int i = 0; i < mat.length; ++i) {

            // Inner loop for columns
            for (int j = 0; j < mat[0].length; ++j) {

                // Storing the maximum element
                max = Math.max(mat[i][j], max);
            }
        }

        // Return the maximum element
        return max;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input 2D matrix
        int mat[][] = { { 1, 3, 4, 19 },
                        { 11, 10, 12, 1 },
                        { 7, 9, 0, 99 } };

        // Calling the method 1 to get max element
        // and storing that integer element
        int max_element = max(mat);

        // Printing the maximum element
        System.out.println(max_element);
    }
}
```

**Output**

```java
99
```

**方法 2:** 利用递归原理

**程序:**

*   递归调用矩阵的每个元素到矩阵的最后一个元素。
*   将当前元素的最大值返回给下一个递归调用元素。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Find the Maximum Element in a Matrix
// Using Recursion

// Importing input output classes
import java.io.*;

// main class
class GFG {

    // Method 1
    // To find the max element
    static int max(int mat[][], int i, int j)

    {
        // Handling the base cases
        if (j == mat[0].length && i < mat.length) {

            // Changing the row and column index
            j = 0;
            ++i;
        }

        // Genric case
        if (i == mat.length) {

            // Simply return
            return 0;
        }

        // By far if we reach here then
        // return the max element
        return Math.max(mat[i][j], max(mat, i, j + 1));
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input 2D array
        int mat[][] = { { 1, 3, 4, 19 },
                        { 11, 10, 12, 1 },
                        { 7, 9, 0, 99 } };
        // Calling the method 1 that is recursie function to
        // find out maximum element
        int max_element = max(mat, 0, 0);

        // Print and display the maximum element
        System.out.println(max_element);
    }
}
```

**Output**

```java
99
```