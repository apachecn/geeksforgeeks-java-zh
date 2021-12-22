# 交换矩阵中任意两行的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到交换-矩阵中任意两行/](https://www.geeksforgeeks.org/java-program-to-interchange-any-two-rows-in-the-matrix/)

给定一个有 m 行 n 列的矩阵。我们必须编写一个 Java 程序来交换给定矩阵中的任意两行。[交换](https://www.geeksforgeeks.org/java-program-to-swap-two-variables/)需要操作来交换两行的元素。交换两行的 O(1)操作是不可能的，因为需要两行之间的完全遍历。

**示例**

```java
Input 1: K = 1, L = 2,

          mat[][] = {{2, 1, 4},
                     {1, 2, 3},  
                     {3, 6, 2}}

Output: 
          mat[][] = {{1, 2, 3},
                     {2, 1, 4},  
                     {3, 6, 2}}

Input 2: K = 1, L = 1,
          mat[][] = {{2, 1, 4},
                     {1, 2, 3}} 

Output: 
          mat[][] = {{2, 1, 4},
                     {1, 2, 3}}   

Input 3: K = 2, L = 3,
          mat[][] =  {{2, 1},
                      {1, 2},  
                      {3, 6}}

Output: 
          mat[][] =  {{2, 1},
                     {3, 6},  
                     {1, 2}}
```

**接近**

*   如果第一个和第二个相同，则按原样打印矩阵。
*   否则在矩阵的第 Kt 行和第 Lt 行上循环。
*   遍历时用两行的索引交换元素。
*   现在循环结束后，打印矩阵。

下面是上述方法的代码实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to interchange
// two row in a Matrix
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
    public static void exchangeAnyTwoRows(int[][] matrix,
                                          int K, int L)
    {
        for (int i = 0; i < matrix[0].length; i++) {

            // Swap two numbers
            int temp = matrix[K - 1][i];
            matrix[K - 1][i] = matrix[L - 1][i];
            matrix[L - 1][i] = temp;
        }

        // Print matrix
        printMatrix(matrix);
    }

    public static void main(String[] args)
    {
        int K = 2, L = 3;
        int mat[][] = { { 2, 1, 4 }, { 1, 2, 3 }, { 3, 6, 2 } };

        // calling the exchange row function
        exchangeAnyTwoRows(mat, K, L);
    }
}
```

**Output**

```java
2 1 4 
3 6 2 
1 2 3 
```

**时间复杂度:** 0(n)，其中 n 为行的长度。

**空间复杂度:** 0(1)