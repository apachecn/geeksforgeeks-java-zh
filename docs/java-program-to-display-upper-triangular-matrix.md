# 显示上三角矩阵的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到显示-上三角矩阵/](https://www.geeksforgeeks.org/java-program-to-display-upper-triangular-matrix/)

上三角矩阵是主矩阵下所有元素都为 0 的矩阵。一个必要条件是矩阵本质上必须是方阵。如果矩阵不是正方形矩阵，就永远不能称为上三角矩阵。

### 例子

```
Input 1: mat[][] = { {2, 1, 4},
                     {1, 2, 3},  
                     {3, 6, 2} }

Output :  mat[][]= { {2, 1, 4},
                     {0, 2, 3},  
                     {0, 0, 2} }

Explaination: All the element below the principal diagonal needs to be 0.

Input 2 :   mat[][]=  { {4,7},
                        {2,8} }

Output :   mat[][]=   { {4,7},
                        {0,8} }

Input 3 :  mat[][]=  { {2,1,4,6},
                       {1,2,3,7},  
                       {3,6,2,8} }  
Output :   Matrix should be a Square Matrix
```

**方法:**

*   If the matrix has equal rows and columns, continue the program; otherwise, exit the program.
*   Run a loop on the whole matrix, and make the element at this position equal to 0 for the row number greater than the column number.

下面是上述方法的实现:

## Java

T0T7**输出**

```
Upper Triangular Matrix is given by :-
2 1 4 
0 2 3 
0 0 2 
```