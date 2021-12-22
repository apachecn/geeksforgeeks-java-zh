# 两个矩阵相减的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序减二矩阵/](https://www.geeksforgeeks.org/java-program-to-subtract-the-two-matrices/)

下面给出了两个矩阵 A 和 B，任务是减去它们，为了减去矩阵，两个矩阵的大小应该相同，即两个矩阵都必须有 N×M 维。

**例:**

```
Input : A[][] = {{3, 1}, 
                 {2, 4}}
        B[][] = {{1, 1}, 
                 {2, 1}}
Output: {{2, 0}, 
         {0, 3}}
Input : A[][] = {{1, 2}, 
                 {3, 4}}
        B[][] = {{6, 4}, 
                 {1, 3}}       
Output: {{-5, -2}, 
         {2, 1}}
```

**方法:**

*   Initialize two matrices of equal size, because to perform subtraction, the two matrices should be the same size.
*   Assign values in two matrices.
*   Create a new matrix with the same size as Matrix1 and Matrix2, and store the result of subtraction.
*   With the help of for loop traversal matrix, the two matrices are subtracted. And store the result in the result matrix.
*   Print the final result matrix.

下面是上述方法的实现:

T3】JavaT5

```
// Java Program to Subtract the Two Matrices

import java.io.*;

class GFG {

    // Function to print Matrix
    static void printMatrix(int M[][], int rowSize,
                            int colSize)
    {
        for (int i = 0; i < rowSize; i++) {
            for (int j = 0; j < colSize; j++)
                System.out.print(M[i][j] + " ");

            System.out.println();
        }
    }

    // Function to subtract the two matrices
    // and store in matrix C
    static int[][] subtract(int A[][], int B[][], int size)
    {
        int i, j;
        int C[][] = new int[size][size];

        for (i = 0; i < size; i++)
            for (j = 0; j < size; j++)
                C[i][j] = A[i][j] + B[i][j];

        return C;
    }

    // Driver code
    public static void main(String[] args)
    {
        int size = 3;

        int A[][] = { { 50, 20, 30 },
                      { 60, 30, 10 },
                      { 30, 80, 10 } };
        // Print the matrices A
        System.out.println("\nMatrix A:");
        printMatrix(A, size, size);

        int B[][] = { { 10, 10, 5 },
                      { 20, 10, 12 },
                      { 23, 21, 12 } };
        // Print the matrices B
        System.out.println("\nMatrix B:");
        printMatrix(B, size, size);

        // Add the two matrices
        int C[][] = subtract(A, B, size);

        // Print the result
        System.out.println("\nResultant Matrix:");
        printMatrix(C, size, size);
    }
}
```

T6T8**输出**T1

**时间复杂度:**O(N×M)，其中 N×M 为矩阵的维数。