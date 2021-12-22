# 检查两个矩阵可乘性的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查两个矩阵的可乘性/](https://www.geeksforgeeks.org/java-program-to-check-the-multiplicability-of-two-matrices/)

给定两个矩阵，检查它们的可乘性的任务。矩阵可以是正方形或矩形。矩阵必须具有相同的数据类型。矩阵的可乘性取决于它们的行和列。如果第一个矩阵的列等于第二个矩阵的行，那么这两个矩阵都是可乘法的。

**示例:**

```
Input : mat1[][] = {{1, 2, 3}, 
                    {4, 5, 6}}
        mat2[][] = {{7,  8 }, 
                    {9,  10},
                    {11, 12}}
Output : Multiplication Possible
     Resultant matrix will have 2X2 dimension.

Input : mat1[][] = {{2, 4}, 
                    {3, 4},
            {1, 2}}
        mat2[][] = {{1, 2}, 
                    {1, 3}}       
Output : Multiplication Not Possible

```

**进场:**

1.  检查两个矩阵的数据类型。
2.  如果数据类型相同，则继续执行程序。
3.  否则，中断程序并打印是不可能的。
4.  如果第一个矩阵中的列数与第二个矩阵中的行数相同，则打印“可能”，所得矩阵的维数为 N×M，其中 N 是第一个矩阵的行数，M 是第二个矩阵的列数。
5.  否则无法打印。

下面是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Check the 
// Multiplicability of Two Matrices

class GFG {

    public static void main(String[] args)
    {
        // Given Two Matrices
        int[][] matrixA = { { 1, 2, 3 }, { 4, 5, 6 } };
        int[][] matrixB
            = { { 7, 8 }, { 9, 10 }, { 11, 12 } };

        int row1 = matrixA.length;
        int column1 = matrixA[0].length;
        int row2 = matrixB.length;
        int column2 = matrixB[0].length;

        if (column1 == row2) {
            System.out.println("Multiplication Possible");
            System.out.println("Resultant matrix will have "
                               + row1 + "X" + column2
                               + " dimension.");
        }
        else
            System.out.println(
                "Multiplication Not Possible");
    }
}
```

**Output**

```
Multiplication Possible
Resultant matrix will have 2X2 dimension.

```