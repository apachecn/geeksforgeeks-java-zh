# 旋转矩阵元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序转矩阵-元素/](https://www.geeksforgeeks.org/java-program-to-rotate-matrix-elements/)

矩阵只是一个二维数组。因此，目标是处理存在元素的固定索引，并对索引执行操作，以便寻址的上的元素应该以随着矩阵旋转而观察的方式交换。这里我们将讨论处理指数的两种方法

1.  使用天真的方法
2.  使用最佳方法

**方法 1:** 使用朴素方法

对于给定的矩阵，任务是顺时针旋转其元素。

**插图:**

```
For 4*4 matrix

Input:
7    8    9
10   11   12
2    3    4

Output:
10   7    8
2    11   9
3    4    12
```

```
For 4*4 matrix

Input:
4    5    6    7    
8    9    10   11
12   13   14   15
16   17   18   19

Output:
8    4    5    6
12   13   9    7
16   14   10   11
17   18   19   15
```

**进场:**

这里，我们将使用循环以螺旋形式打印元素。其中，我们将从最外面的一个开始，逐个旋转元素的所有环。为了旋转环，我们需要做以下工作:

1.  移动顶行的元素，
2.  移动最后一列的元素，
3.  移动底部行的元素，并
4.  移动第一列的元素。

此外，如果有内环，重复上述步骤。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Rotate Matrix Elements

// Importing classes from java.lang package 
import java.lang.*;
// Importing classes from java.util package 
import java.util.*;

// main Class 
class GFG {
    static int r = 4;
    static int c = 4;

    // Method  
    // To rotate a matrix of
    // dimension r x c. And initially,
    // p = r and q = c
    static void rotate_matrix(int p, int q, int matrix[][])
    {
        int rw = 0, cl = 0;
        int previous, current;

        // rw is the Staring row index
        // p is the ending row index
        // cl is the starting column index
        // q is the ending column index and
        // x is the iterator
        while (rw < p && cl < q) {

            if (rw + 1 == p || cl + 1 == q)
                break;

            // After storing the first element of the
            // next row, this element will substitute
            // the first element of the current row
            previous = matrix[rw + 1][cl];

            // Moving the elements of the first row
            // from rest of the rows
            for (int x = cl; x < q; x++) {
                current = matrix[rw][x];
                matrix[rw][x] = previous;
                previous = current;
            }
            rw++;

            // Moving the elements of the last column
            // from rest of the columns
            for (int x = rw; x < p; x++) {
                current = matrix[x][q - 1];
                matrix[x][q - 1] = previous;
                previous = current;
            }
            q--;

            // Moving the elements of the last row
            // from rest of the rows
            if (rw < p) {
                for (int x = q - 1; x >= cl; x--) {
                    current = matrix[p - 1][x];
                    matrix[p - 1][x] = previous;
                    previous = current;
                }
            }
            p--;

            // Moving elements of the first column
            // from rest of the rows
            if (cl < q) {
                for (int x = p - 1; x >= rw; x--) {
                    current = matrix[x][cl];
                    matrix[x][cl] = previous;
                    previous = current;
                }
            }
            cl++;
        }

        // Prints the rotated matrix
        for (int x = 0; x < r; x++) {
            for (int y = 0; y < c; y++)
                System.out.print(matrix[x][y] + " ");
            System.out.print("\n");
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Custom input array
        int b[][] = { { 5, 6, 7, 8 },
                      { 1, 2, 3, 4 },
                      { 0, 15, 6, 5 },
                      { 3, 1, 2, 12 } };

        // Calling function(Method1) to rotate matrix
        rotate_matrix(r, c, b);
    }
}
```

**Output**

```
1 5 6 7 
0 15 2 8 
3 6 3 4 
1 2 12 5 
```

**方法 2:** 采用最优方法

对于给定的 M×N 大小的矩阵，我们需要将矩阵元素向右旋转 *k* 次。其中 *k* 是一个数字。

**进场:**

最佳方法是将所述矩阵的每一行观察为一个数组，然后执行数组旋转。这是通过利用临时数组将矩阵的元素从给定的数字 *k* 复制到数组的末尾到数组的开始来实现的。然后剩下的元素从开始到( *k* -1)到结束一个数组。

插图:

```
Input : M = 3, N = 3, k = 2
        1 2 3
        4 5 6
        7 8 9  

Output : 2 3 1
         5 6 4
         8 9 7 

Input : M = 2, N = 2, k = 2
        11 12
        13 14

Output : 11 12
         13 14
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Rotate Matrix to Right Side by K Times

// Main Class
public class GFG {

    // Dimension of the matrix

    // Initializing to custom values
    static final int P = 3;
    static final int Q = 3;

    // Method 1
    // To rotate the stated matrix by K times
    static void rotate_Matrix(int mat[][], int K)
    {
        // Using temporary array of dimension P
        int tempo[] = new int[P];

        // Rotating matrix by k times across the size of
        // matrix
        K = K % P;

        for (int j = 0; j < Q; j++) {

            // Copying first P-K elements
            // to the temporary array
            for (int l = 0; l < P - K; l++)
                tempo[l] = mat[j][l];

            // Copying the elements of the matrix
            // from K to the end to the starting
            for (int x = P - K; x < P; x++)
                mat[j][x - P + K] = mat[j][x];

            // Copying the elements of the matrix
            // from the temporary array to end
            for (int x = K; x < P; x++)
                mat[j][x] = tempo[x - K];
        }
    }

    // Method 2
    // To show the resultant matrix
    static void show_Matrix(int mat[][])
    {
        for (int j = 0; j < Q; j++) {
            for (int x = 0; x < P; x++)
                System.out.print(mat[j][x] + " ");
            System.out.println();
        }
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input array
        int mat[][]
            = { { 1, 2, 5 }, { 3, 4, 6 }, { 8, 10, 9 } };

        // Custom value of K
        int K = 2;

        // Calling the above created method for
        // rotating matrix by k times
        rotate_Matrix(mat, K);

        // Calling the above method for
        // displaying rotated matrix
        show_Matrix(mat);
    }
}
```

**Output**

```
2 5 1 
4 6 3 
10 9 8 
```