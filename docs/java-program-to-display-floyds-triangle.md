# 显示弗洛伊德三角形的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到显示-floyds-triangle/](https://www.geeksforgeeks.org/java-program-to-display-floyds-triangle/)

[弗洛伊德三角形](http://en.wikipedia.org/wiki/Floyd%27s_triangle)是第一自然数的三角形。这是数字/值或模式的正确排列。基本上**、**是直角三角形中自然数从左到右的排列

**说明:**假设要显示的行数为 5，那么期望的输出应该显示 5 行，如下所示:

```java
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```

**算法:**

1.  变量初始化
    *   在内存中创建保存行和列的变量。
    *   创建并初始化要显示的变量保持模式或值。
2.  使用嵌套 for 循环遍历行和列。
    *   行的外部循环。
    *   当前行中列的内部循环。
3.  在嵌套循环之外初始化时，根据执行处理保存动态值的变量。
    *   如果要显示值，在行的循环内和列的外部循环内递增该变量。
    *   如果要显示模式，在创建时指定循环外的字符，并且在任何循环中不改变持有者值。

**实现:**弗洛伊德三角

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to display Floyd's triangle

// Importing Java libraries
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // No of rows to be printed
        int n = 5;

        // Creating and initializing variable for
        // rows, columns and display value
        int i, j, k = 1;

        // Nested iterating for 2D matrix
        // Outer loop for rows
        for (i = 1; i <= n; i++) {

            // Inner loop for columns
            for (j = 1; j <= i; j++) {

                // Printing value to be displayed
                System.out.print(k + "  ");

                // Incremeting value displayed
                k++;
            }

            // Print elements of next row
            System.out.println();
        }
    }
}
```

**Output**

```java
1  
2  3  
4  5  6  
7  8  9  10  
11  12  13  14  15
```