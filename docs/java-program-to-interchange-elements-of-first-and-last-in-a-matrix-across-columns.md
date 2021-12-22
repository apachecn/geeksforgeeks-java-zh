# 跨列交换矩阵中第一个和最后一个元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到交换-跨列矩阵中第一个和最后一个元素/](https://www.geeksforgeeks.org/java-program-to-interchange-elements-of-first-and-last-in-a-matrix-across-columns/)

对于给定的 4 x 4 矩阵，任务是交换第一列和最后一列的元素，然后返回结果矩阵。

**示例:**

```java
Input 1 :   1  1  5  0
            2  3  7  2
            8  9  1  3
            6  7  8  2

Output 1 :  0  1  5  1
            2  3  7  2
            3  9  1  8
            2  7  8  6

Input 2 :   7   8  9  10
           11  13  14  1
           15   7  12 22
           11  21  30  1

Output 2 : 10  8   9   7
           1  13  14  11
           22  7  12  15
           1  21  30  11
```

**进场:**

为了获得所需的输出，我们需要交换所述矩阵的第一列和最后一列的元素。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Interchange Elements of the
// First and Last Column in a Matrix

// Importing input output classes
import java.io.*;

class GFG {

    // Declare static variable and initialize to
    // order of the matrix
    static int N = 3;

    // Method 1
    // To swap first and last column in a matrix
    static void Swap_First_Last(int mat[][])
    {
        int cls = N;

        // Interchanging of elements between the
        // first and last columns
        for (int j = 0; j < N; j++) {
            int temp = mat[j][0];
            mat[j][0] = mat[j][N - 1];
            mat[j][N - 1] = temp;
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Creating 2D integer element matrix
        // Custom input matrix
        int mat[][]
            = { { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };

        // Outer loop for rows
        for (int j = 0; j < N; j++) {

            // Inner loop for columns
            for (int k = 0; k < N; k++) {

                // Print the input matrix
                System.out.print(mat[j][k] + " ");
            }
            // Operations over a row is computed so new line
            System.out.println();
        }

        System.out.println("Swapped Matrix as follows : ");

        // Now, calling the (Method1) to interchange
        // first and last columns in above matrix
        Swap_First_Last(mat);

        // Now simply print the updated matrix
        // Swapped matrix using nested for loops

        // Outer loop for rows
        for (int j = 0; j < N; j++) {

            // Inner loop for columns
            for (int k = 0; k < N; k++)

                // Print the swapped matrix
                System.out.print(mat[j][k] + " ");

            // Operations over a row is computed so new line
            System.out.println();
        }
    }
}
```

**Output**

```java
1 2 3 
4 5 6 
7 8 9 
Swapped Matrix as follows : 
3 2 1 
6 5 4 
9 8 7 

```