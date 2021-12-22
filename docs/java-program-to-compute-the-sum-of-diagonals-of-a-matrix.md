# 计算矩阵对角线之和的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序计算矩阵对角线之和/](https://www.geeksforgeeks.org/java-program-to-compute-the-sum-of-diagonals-of-a-matrix/)

对于给定的 2D 方阵，任务是找出主对角线和次对角线上的元素之和。例如，分析以下 4 × 4 输入矩阵。

```java
a00 a01 a02 a03
a10 a11 a12 a13
a20 a21 a22 a23
a30 a31 a32 a33
```

**进场:**

**1。**主对角线由元素 a00、a11、a22、a33 构成，主对角线的行列条件为

```java
row = column
```

**2。**然而，次对角线由元素 a03、a12、a21、a30 构成，并且次对角线的行列条件为

```java
row = number_of_rows – column -1
```

插图:

```java
Input 1 : 6 7 3 4
           8 9 2 1
           1 2 9 6
           6 5 7 2

Output 1 : *Principal Diagonal:* 26
 *Secondary Diagonal:* 14

Input 2 : 2 2 2
          1 1 1
          3 3 3

Output 2 : *Principal Diagonal:* 6
 *Secondary Diagonal:* 6
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Find the Sum of Diagonals of a Matrix

// Importing input output classes
import java.io.*;

// Main Class
public class GFG {

    // Method 1
    // To calculate Sum of Diagonals
    static void Sum_of_Diagonals(int[][] matrix, int N)
    {

        // Declaring and initializing two variables to zero
        // initially for primary and secondary diagonal
        // count
        int Pd = 0, Sd = 0;

        // Two Nested for loops for iteration over a matrix

        // Outer loop for rows
        for (int k = 0; k < N; k++) {

            // Inner loo pfo columns
            for (int l = 0; l < N; l++) {

                // Condition for the principal
                // diagonal
                if (k == l)
                    Pd += matrix[k][l];

                // Condition for the secondary diagonal
                if ((k + l) == (N - 1))
                    Sd += matrix[k][l];
            }
        }

        // Print and display the sum of primary diagonal
        System.out.println("Sum of Principal Diagonal:"
                           + Pd);
        // Print and display the sum of secondary diagonal
        System.out.println("Sum of Secondary Diagonal:"
                           + Sd);
    }

    // Method 2
    // Main driver method
    static public void main(String[] args)
    {

        // Input integer array
        // Custom entries in an array
        int[][] b = { { 8, 2, 13, 4 },
                      { 9, 16, 17, 8 },
                      { 1, 22, 3, 14 },
                      { 15, 6, 17, 8 } };

        // Passing the array as an argument to the function
        // defined above(Method1-to compute sum of
        // diagonals)
        Sum_of_Diagonals(b, 4);
    }
}
```

**Output**

```java
Sum of Principal Diagonal:35
Sum of Secondary Diagonal:58
```