# 以三角形形式打印乘法表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-print-the-乘法表-in-a-triangle-form/](https://www.geeksforgeeks.org/java-program-to-print-the-multiplication-table-in-a-triangle-form/)

在这种形式中，表格是按行和列显示的，在每一行中，只有相同列号的条目被填充。

**例:**

```
Input : rows = 6
Output:
    1
    2 4
    3 6 9
    4 8 12 16
    5 10 15 20 25
    6 12 18 24 30 36  
```

**方法:**思路是使用嵌套循环。首先，显示列号。然后，使用到嵌套循环来填充行的条目。

1.  In the function owner (), first enter the number of rows n.
2.  The loop is (I = 0；; One < row; ++) is used to print the column number line.
3.  The loop is (I = 0；; I < line; I++) for printing n rows of entries. 4\. The nested loop of (j = 0；; j<= I； J++) for printing the current entry.

下面是上述方法的实现。

## 爪哇

```
// Java Program to Print the Multiplication
// Table in Triangular Form

import java.util.*;

public class MultiplicationTableTrianglePattern {

    // Function to print tables in triangular form

    public static void main(String args[])
    {
        int rows, i, j;

        Scanner in = new Scanner(System.in);

        rows = 6;

        // Loop to print multipliacation
        // table in triangular form

        for (i = 1; i <= rows; i++) {
            for (j = 1; j <= i; j++) {
                System.out.print(i * j + " ");
            }
            System.out.println();
        }
    }
}
```

**输出**

```
1 
2 4 
3 6 9 
4 8 12 16 
5 10 15 20 25 
6 12 18 24 30 36 

```

**时间复杂度:** O(n <sup>2</sup> ，其中 n 为行数。