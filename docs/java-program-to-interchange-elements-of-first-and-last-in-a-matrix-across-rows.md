# 跨行交换矩阵中第一个和最后一个元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到交换-跨行矩阵中的第一个和最后一个元素/](https://www.geeksforgeeks.org/java-program-to-interchange-elements-of-first-and-last-in-a-matrix-across-rows/)

对于给定的 4 × 4 矩阵，任务是交换第一行和最后一行的元素，然后返回结果矩阵。

插图:

```java
Input 1:  1  1  5  0
          2  3  7  2
          8  9  1  3
          6  7  8  2
Output 1: 6  7  8  2
          2  3  7  2 
          8  9  1  3
          1  1  5  0

Input 2:  7   8   9  10
         11  13  14   1
         15   7  12  22
         11  21  30   1

Output 2: 11  21  30   1
         11  13  14   1
         15  7   12  22
         7   8   9   10
```

**进场:**

为了获得所需的输出，我们需要交换所述矩阵的第一行和最后一行的元素。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Interchange Elements of First
// and Last Row in a Matrix

// Importing input output classes
import java.io.*;

// Main Class
public class GFG {

    // Method 1
    // To swap First and Last Row
    static void swap_First_last(int mat[][])
    {
        int rws = mat.length;

        // Interchanging of elements between the
        // first and last rows
        for (int j = 0; j < mat[0].length; j++) {

            // Using temporary variable so in order
            // not to loose the values of the matrix
            // Simply, swapping the values stored
            int temp = mat[0][j];
            mat[0][j] = mat[rws - 1][j];
            mat[rws - 1][j] = temp;
        }
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
        throws IOException
    {
        // Input integer matrix
        int mat[][] = { { 2, 3, 4, 5 },
                        { 8, 9, 6, 15 },
                        { 13, 22, 11, 18 },
                        { 19, 1, 2, 0 } };

        // Display message only
        System.out.println("Input matrix is as follows : ");

        // Printing the Input matrix
        for (int j = 0; j < mat.length; j++) {
            for (int k = 0; k < mat[0].length; k++)

                // Print the elements of the input matrix
                System.out.print(mat[j][k] + " ");

            // New line as row ended
            System.out.println();
        }

        System.out.println(
            "Swapped matrix is as follows : ");

        // Calling the (method1) to swap rows in a matrix
        swap_First_last(mat);

        // Printing the Swapped matrix
        for (int j = 0; j < mat.length; j++) {
            for (int k = 0; k < mat[0].length; k++)

                // Print the elements of the swapped matrix
                System.out.print(mat[j][k] + " ");

            // New line as row ended
            System.out.println();
        }
    }
}
```

**Output:**

```java
Input matrix is as follows : 
2 3 4 5 
8 9 6 15 
13 22 11 18 
19 1 2 0 
Swapped matrix is as follows : 
19 1 2 0 
8 9 6 15 
13 22 11 18 
2 3 4 5

```