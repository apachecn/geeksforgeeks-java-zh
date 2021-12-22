# 接受 M×N 阶矩阵的 Java 程序&交换对角线

> 原文:[https://www . geesforgeks . org/Java-program-to-accept-a-matrix-order-m-x-n-interchange-the-对角线/](https://www.geeksforgeeks.org/java-program-to-accept-a-matrix-of-order-m-x-n-interchange-the-diagonals/)

**问题描述:**编写一个 Java 程序，接受一个 **M × N** 阶的矩阵，然后交换矩阵的对角线。

**步骤:**

1.我们只能把对角线换成正方形矩阵。

2.创建一个大小为[M × M]的正方形矩阵。

3.检查矩阵是否为正方形矩阵。如果矩阵是正方形的，那么按照步骤 3，否则终止程序。

4.应用逻辑交换矩阵的对角线下面给出了一些逻辑。

**方法 1:** 互换元素 **a[i][i]** 和**a[I][n–I-1]**

> for(j = 0；j < m；j++){ 0
> 
> temp = a[j][j]；
> 
> a[j][j]= a[j][n–1–j]；
> 
> a[j][n–1–j]=温度；
> 
> }

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
//  Java Program to Accept a Matrix of Order M x N &
//  Interchange the Diagonals

import java.util.Scanner;
public class InterchangeDiagonals {
    public static void main(String[] args)
    {
        // declare variable
        int m, n, i, j, temp;

        // create a object of scanner class
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of rows ");

        // take number of rows
        m = sc.nextInt();

        System.out.print("Enter number of columns ");

        // take number of columns
        n = sc.nextInt();

        // declare a mxn order array
        int a[][] = new int[m][n];

        // if block it's execute when m is equals to n
        if (m == n) {
            System.out.println(
                "Enter all the values of matrix ");

            // take the matrix inputs
            for (i = 0; i < m; i++) {
                for (j = 0; j < n; j++) {
                    a[i][j] = sc.nextInt();
                }
            }

            System.out.println("original Matrix:");

            // print the original matrix
            for (i = 0; i < m; i++) {
                for (j = 0; j < n; j++) {
                    System.out.print(a[i][j] + " ");
                }
                System.out.println("");
            }

            // perform interchange
            for (j = 0; j < m; j++) {
                temp = a[j][j];
                a[j][j] = a[j][n - 1 - j];
                a[j][n - 1 - j] = temp;
            }
            System.out.println(
                " after interchanging diagonals of matrix ");

            // print interchanged matrix
            for (i = 0; i < m; i++) {
                for (j = 0; j < n; j++) {
                    System.out.print(a[i][j] + " ");
                }
                System.out.println("");
            }
        }

        // else block it's only execute when m is not equals
        // to n
        else {
            System.out.println("Rows not equal to columns");
        }
    }
}
```

**输出:**

> 输入行数 3
> 
> 输入列数 3
> 
> 输入矩阵的所有值
> 
> one
> 
> Two
> 
> three
> 
> four
> 
> five
> 
> six
> 
> seven
> 
> eight
> 
> nine
> 
> 原始矩阵:
> 
> 1   2   3  
> 
> 4   5   6  
> 
> 7   8   9  
> 
> 交换矩阵的对角线后
> 
> 3   2   1  
> 
> 4   5   6  
> 
> 9   8   7

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
//  Java Program to Accept a Matrix of Order MxN &
//  Interchange the Diagonals

import java.util.Scanner;
public class InterchangeDiagonals {
    public static void main(String[] args)
    {
        // declare variable
        int m, n, i, j, temp;

        // create a object of scanner class
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of rows ");

        // take number of rows
        m = sc.nextInt();

        System.out.print("Enter number of columns ");

        // take number of columns
        n = sc.nextInt();

        // declare a mxn order array
        int a[][] = new int[m][n];

        // if block it's execute when m is equals to n
        if (m == n) {
            System.out.println(
                "Enter all the values of matrix ");

            // take input matrix
            for (i = 0; i < m; i++) {
                for (j = 0; j < n; j++) {
                    a[i][j] = sc.nextInt();
                }
            }

            System.out.println("original Matrix:");

            // print original matrix
            for (i = 0; i < m; i++) {
                for (j = 0; j < n; j++) {
                    System.out.print(a[i][j] + " ");
                }
                System.out.println("");
            }

            // performing interchange
            for (j = 0; j < m; j++) {
                temp = a[j][j];
                a[j][j] = a[j][n - 1 - j];
                a[j][n - 1 - j] = temp;
            }
            System.out.println(
                " after interchanging diagonals of matrix ");

            // print interchanged matrix
            for (i = 0; i < m; i++) {
                for (j = 0; j < n; j++) {
                    System.out.print(a[i][j] + " ");
                }
                System.out.println("");
            }
        }

        // else block it's only execute when m is not equals
        // to n
        else {
            System.out.println("Rows not equal to columns");
        }
    }
}
```

**输出:**

> 输入行数 2
> 
> 输入列数 1
> 
> 输入矩阵的所有值
> 
> one
> 
> Two
> 
> 行不等于列