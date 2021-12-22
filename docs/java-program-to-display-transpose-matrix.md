# 显示转置矩阵的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到显示-转置-矩阵/](https://www.geeksforgeeks.org/java-program-to-display-transpose-matrix/)

矩阵的转置是通过将行变为列，将列变为行来实现的。换句话说，A[][]的转置是通过将 A[i][j]改为 A[j][i]而获得的。

![matrix-transpose](img/e368eb2a9ca0cd036dc0c86015b59151.png)

**进场:**

*   创建二维数组。
*   通过运行两个嵌套循环在数组中插入值。外部第 I 个循环将一直运行到行数，内部第 jth 个循环将一直运行到列数。
*   为了显示矩阵的转置，运行与上面步骤中解释的相同的循环，但是每次遍历循环内部时打印第 a[j[i]个元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Display Transpose Matrix

import java.util.*;
public class GFG {
    public static void main(String args[])
    {
        // initialize the array of 3*3 order
        int[][] arr = new int[3][3];

        System.out.println("enter the elements of matrix");

        int k = 1;

        // get the elements from user
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                arr[i][j] = k++;
            }
        }

        System.out.println("Matrix before Transpose ");

        // display original matrix
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                System.out.print(" " + arr[i][j]);
            }
            System.out.println();
        }

        System.out.println("Matrix After Transpose ");

        // transpose and print matrix
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                System.out.print(" " + arr[j][i]);
            }
            System.out.println();
        }
    }
}
```

**Output**

```
enter the elements of matrix
Matrix before Transpose 
 1 2 3
 4 5 6
 7 8 9
Matrix After Transpose 
 1 4 7
 2 5 8
 3 6 9
```