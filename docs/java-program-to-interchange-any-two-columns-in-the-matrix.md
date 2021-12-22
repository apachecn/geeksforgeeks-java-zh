# 交换矩阵中任意两列的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到交换-矩阵中任意两列/](https://www.geeksforgeeks.org/java-program-to-interchange-any-two-columns-in-the-matrix/)

给定一个有 m 行 n 列的矩阵。我们必须编写一个 Java 程序来交换给定矩阵中的任意两列(即输入中没有 K 和 L 的列)。[交换](https://www.geeksforgeeks.org/swap-two-numbers-without-using-temporary-variable/)需要操作来交换两列的元素。O(1)交换两列的操作是不可能的，因为需要两列之间的完全遍历。

### 例子

```java
Input 1: K = 1, L = 2,
        mat[][] = {{2, 1, 4},
                   {1, 2, 3},  
                   {3, 6, 2}}

Output: mat[][] = {{1,2, 4},
                   {2,1, 3},  
                   {6,3, 2}}

Input 2: K = 1, L = 1,
             mat[][] = {{2, 1, 4},
                        {1, 2, 3}}

Output: mat[][] = {{2, 1, 4},
                   {1, 2, 3}}

Input 3: K = 1, L = 3,
              mat[][] = {{2, 1,8},
                         {1, 2,9},  
                         {3, 6,5}}   

Output:    {{8, 1,2},
            {9, 2,1},  
            {5, 6,3}}                        
```

### 方法

*   如果我们要交换的列号是相同的，那么就按原样打印矩阵。
*   否则在矩阵的第 Kt 列和第 Lt 列上循环。
*   遍历时，用两列的索引交换的元素。
*   现在循环结束后，打印矩阵。

以下是上述方法的代码实现:

## Java

```java
// Java program to interchange
// two Column in a Matrix
import java.io.*;
class GFG {

    public static void printMatrix(int[][] matrix)
    {
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++)
                System.out.print(matrix[i][j] + " ");
            System.out.println();
        }
    }
    public static void exchangeAnyTwoColumns(int[][] matrix,
                                             int K, int L)
    {
        for (int i = 0; i < matrix.length; i++) {

            // Swap two numbers
            int temp = matrix[i][K - 1];
            matrix[i][K - 1] = matrix[i][L - 1];
            matrix[i][L - 1] = temp;
        }

        // Print matrix
        printMatrix(matrix);
    }

    public static void main(String[] args)
    {
        int K = 1, L = 2;
        int mat[][]
            = { { 2, 1, 4 }, { 1, 2, 3 }, { 3, 6, 2 } };

        // calling the exchange Column function
        exchangeAnyTwoColumns(mat, K, L);
    }
}
```

**输出**

```java
1 2 4 
2 1 3 
6 3 2 
```

**时间复杂度:** 0(n)，其中 n 为列的长度。

**空间复杂度:** 0(1)