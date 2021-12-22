# 确定给定矩阵是否为稀疏矩阵的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序确定给定矩阵是否是稀疏矩阵/](https://www.geeksforgeeks.org/java-program-to-determine-if-a-given-matrix-is-a-sparse-matrix/)

矩阵是具有 m 行和 n 列的二维数据对象，因此总共有 m*n 个值。如果一个矩阵的大部分值都是 0，那么我们说这个矩阵叫做**稀疏矩阵**。因此，我们的目标是计算矩阵中出现的 0 的数量。如果它们超过矩阵中元素的一半，则打印**是**，否则**否**作为输出。

**例:**

```java
Input:  1 0 3
        0 0 4
        6 0 0
Output: Yes
Explaination:There are 5 zeros in the matrix which 
          is more than half of the matrix size.

Input:  1 2 3
        0 7 8
        5 0 7 
Output: No 
Explaination:There are 2 zeros in the matrix which 
             is less than half of the matrix size.

```

要检查一个矩阵是否是稀疏矩阵，我们只需要检查等于零的元素总数。如果该计数大于(m * n)/2，则打印“是”或“否”。有两种方法可以做到这一点。

在这种方法中，我们将检查矩阵是否是稀疏矩阵。

1.  Take the matrix.
2.  Traverse the elements of the matrix one by one and count the number of zeros.
3.  Check whether the count is greater than (m*n)/2, if so, no.

下面是上述方法的实现:

T3】JavaT5

```java
// Java Program to Determine if a given
// Matrix is a Sparse Matrix

// Importing Libraries
import java.io.*;

class GFG {

    // Driver Function
    public static void main(String args[])
    {
        // Initialising and declaring
        // variables and array

        int array[][]
            = { { 1, 0, 3 }, { 0, 0, 4 }, { 6, 0, 0 } };

        int m = 3;
        int n = 3;
        int counter = 0;

        // Count number of zeros in the matrix

        for (int i = 0; i < m; ++i)
            for (int j = 0; j < n; ++j)
                if (array[i][j] == 0)
                    ++counter;

        // Printing result

        if (counter > ((m * n) / 2))
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(m*n)