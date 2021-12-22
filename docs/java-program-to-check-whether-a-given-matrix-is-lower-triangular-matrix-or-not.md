# 检查给定矩阵是否为下三角矩阵的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-check-给定矩阵是否为下三角矩阵/](https://www.geeksforgeeks.org/java-program-to-check-whether-a-given-matrix-is-lower-triangular-matrix-or-not/)

在下三角矩阵中，对角线上方的元素应为 0。给定一个矩阵，任务是检查矩阵是否为下三角形式。矩阵必须是正方形矩阵。如果主对角线以上的所有条目都为零，则正方形矩阵称为下三角形。

**示例–**

```
Input:
    1    0    0
    1    2    0
    1    2    3

Output: Matrix is lower triangular matrix

Input:
    1    2    2
    2    1    1
    2    2    2

Output: Matrix is not a lower triangular matrix
```

**进场:**

1.  Check whether the given matrix is square.
2.  If so, traverse the upper triangular partial matrix.
3.  Check whether all items above the main diagonal are zero.
4.  If so, then the printing matrix is a lower triangular matrix.

下面是上述方法的实现:

## Java

```
// Java Program to check for
// a lower triangular matrix.

import java.util.Scanner;

public class LowerTriangularMatrix {
    public static boolean
    isLowerTriangularMatrix(int[][] matrix)
    {
        for (int i = 0; i < matrix[0].length; i++) {
            for (int j = i + 1; j < matrix[0].length; j++) {
                if (matrix[i][j] != 0)
                    return false;
            }
        }
        return true;
    }
    public static void main(String args[])
    {
        int rows = 3, columns = 3;

        // returns true if number of rows and columns are
        // equal else false
        if (rows == columns) {
            // initializing the matrix
            int Matrix[][]
                = { { 1, 0, 0 }, { 2, 3, 0 }, { 5, 6, 7 } };

            // Display the values of matrix
            System.out.println("Matrix is : ");
            for (int i = 0; i < rows; i++) {
                for (int j = 0; j < columns; j++) {
                    System.out.print(Matrix[i][j] + "\t");
                }
                System.out.println();
            }

            // Function call
            boolean result
                = isLowerTriangularMatrix(Matrix);

            // returns true if matrix is lower triangular
            // matrix else false
            if (result == true) {
                System.out.println(
                    "Matrix is lower triangular matrix");
            }
            else {
                System.out.println(
                    "Matrix is not lower triangular matrix");
            }
        }
        else {
            System.out.println(
                "Number of rows and number of columns should be equal");
        }
    }
}
```

**输出**

```
Matrix is : 
1    0    0    
2    3    0    
5    6    7    
Matrix is lower triangular matrix

```

**时间复杂度:** O(N <sup>2</sup> ，其中 N 为正方形矩阵中行的长度。