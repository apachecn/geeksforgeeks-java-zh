# 使用迭代方法添加两个矩阵的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序加二-矩阵-使用-迭代-方法/](https://www.geeksforgeeks.org/java-program-to-add-two-matrix-using-iterative-approach/)

给定两个矩阵 **A** 和 **B** ，使用 Java 中的迭代方法添加两个矩阵，比如 for 循环、while 循环、do-while 循环。对于两个矩阵的加法，必要条件是两个矩阵必须具有相同的大小，加法必须对两个矩阵进行完全迭代。

**示例**

```
Input: A[][] = {{1, 3}, 
                {2, 4}}
       B[][] = {{1, 1}, 
                {1, 1}}
Output: {{2, 4}, 
         {3, 5}}

Input: A[][] = {{1, 2}, 
                {4, 8}}
       B[][] = {{2, 4}, 
                {6, 8}}       
Output: {{3, 6}, 
         {10, 16}

```

**迭代方法**

*   Take two matrices to be added
*   Create a new matrix to store the sum of two matrices.
*   Traverse each element of two matrices and add them. Store this sum at the corresponding index in the new matrix.
*   Print the final new matrix.

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Add Two 
// Matrix Using Iterative Approach
import java.io.*;
class Main {

    // Print matrix using iterative approach
    public static void printMatrix(int[][] a)
    {
        for (int i = 0; i < a.length; i++) {
            for (int j = 0; j < a[0].length; j++)
                System.out.print(a[i][j] + " ");
            System.out.println();
        }
    }
    // Sum of two matrices using Iterative approach
    public static void matrixAddition(int[][] a, int[][] b)
    {
        int[][] sum = new int[a.length][a[0].length];
        for (int i = 0; i < a.length; i++) {
            for (int j = 0; j < a[0].length; j++)
                sum[i][j] = a[i][j] + b[i][j];
        }

        // printing the matrix
        printMatrix(sum);
    }
    public static void main(String[] args)
    {
        int[][] firstMat = { { 1, 3 }, { 2, 4 } };
        int[][] secondMat = { { 1, 1 }, { 1, 1 } };
        System.out.println("The sum is ");

        // calling the function
        matrixAddition(firstMat, secondMat);
    }
}
```

**Output**

```
The sum is 
2 4 
3 5 

```

**时间复杂度:** O(n*m)，其中 N X M 为矩阵的维数。

**空间复杂度:-** O(n*m)