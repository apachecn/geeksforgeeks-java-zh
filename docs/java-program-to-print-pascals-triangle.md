# 打印帕斯卡三角形的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到打印-帕斯卡-三角形/](https://www.geeksforgeeks.org/java-program-to-print-pascals-triangle/)

帕斯卡三角形是一种基于 nCr 的三角形模式，下图是帕斯卡三角形的图示。

**例:**

```java
Input : N = 5
Output:
          1
        1   1
      1   2   1
    1   3   3   1
  1   4   6   4   1
1   5   10   10   5   1
```

**方法#1:**

nCr 公式:

> n！/(n–r)！r！

使用 nCr 公式后，图示变为:

```java
           0C0
        1C0   1C1
     2C0   2C1   2C2
  3C0   3C1   3C2   3C3
```

**<u>算法:</u>**

*   Take the number of lines to print, assuming n.
*   Perform outer iteration I from 0 to n times to print lines.
*   Iterate internally for j from 0 to (n–1).
*   Print a single space ""
*   Close inner loop (J loop)//Left spacing required
*   Iterate internally for j from 0 to i.
*   Print nCr of I and J
*   Close the inner loop.
*   Print line breaks after each internal iteration (\n).

下面是上述方法的实现:

T3】JavaT5

```java
// Print Pascal's Triangle in Java
import java.io.*;

class GFG {
    public int factorial(int i)
    {
        if (i == 0)
            return 1;
        return i * factorial(i - 1);
    }
    public static void main(String[] args)
    {
        int n = 4, i, j;
        GFG g = new GFG();
        for (i = 0; i <= n; i++) {
            for (j = 0; j <= n - i; j++) {

                // for left spacing
                System.out.print(" ");
            }
            for (j = 0; j <= i; j++) {

                // nCr formula
                System.out.print(
                    " "
                    + g.factorial(i)
                          / (g.factorial(i - j)
                             * g.factorial(j)));
            }

            // for newline
            System.out.println();
        }
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N <sup>2</sup> )

**接近#2:**

行号*行*的第一个条目是二项式系数 *C(行，i)* ，所有行都以值 1 开始。思路是用 *C(线，i-1)* 计算 *C(线，i)* 。

```java
C(line, i) = C(line, i-1) * (line - i + 1) / i
```

以下是给定方法的实现:

## Java

```java
// Print Pascal's Triangle in Java
import java.io.*;
class GFG {

    // Pascal function
    public static void printPascal(int n)
    {
        for (int line = 1; line <= n; line++) {
            for (int j = 0; j <= n - line; j++) {

                // for left spacing
                System.out.print(" ");
            }

            // used to represent C(line, i)
            int C = 1;
            for (int i = 1; i <= line; i++) {

                // The first value in a line is always 1
                System.out.print(C + " ");
                C = C * (line - i) / i;
            }
            System.out.println();
        }
    }

    // Driver code
    public static void main(String[] args)
    {
        int n = 4;
        printPascal(n);
    }
}
```

**输出**

```java
    1 
   1 1 
  1 2 1 
 1 3 3 1 
```

**时间复杂度:** O(N <sup>2</sup> )