# 打印星形帕斯卡三角形的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-print-star-Pascal-triangle/](https://www.geeksforgeeks.org/java-program-to-print-star-pascals-triangle/)

[帕斯卡三角形](http://en.wikipedia.org/wiki/Pascal's_triangle)是二项式系数的三角形数组。写一个以整数值 n 为输入的函数，打印帕斯卡三角形的前 n 行。下面是帕斯卡三角形的前 6 行。在这篇文章中，我们将研究印刷帕斯卡三角形的过程。帕斯卡三角形是一种基于 nCr 的三角形模式，下图是帕斯卡三角形的图示。

![](img/de27c3e15c24496f3d5635741c6c6b90.png)

插图:

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

**方法:**

有两种方法可以达到同样的效果。我们去看看。

1.  使用 nCr 公式
2.  使用二项式系数

**方法 1:** 使用 nCr 公式

**实现:**使用 nCr 公式按照下面的算法打印帕斯卡三角形

*   假设 n 是要打印的行数
*   使用从 0 到 k 次的外部迭代 a 打印行
*   从 0 到(K–1)对 b 进行内部迭代。
*   然后将空格打印为" "。
*   关闭内部“b”循环。
*   对 b 进行从“0”到“a”的内部迭代。
*   “a”和“b”的输出 nCr。
*   闭合内环。
*   每次内部迭代后打印换行符(\n)。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Print Pascal's Triangle

// Importing input output classes
import java.io.*;

// Main Class
public class GFG {

    // Method 1
    // To find factorial of a number
    public int factorial(int a)
    {
        // Edge case
        // Factorial of 0 is unity
        if (a == 0)

            // Hence return 1
            return 1;

        // else recursively call the function over the
        // number whose facoial is to be computed
        return a * factorial(a - 1);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Declare and initialize number whose
        // factorial is to be computed
        int k = 4;

        int a, b;

        // Creating an object of GFG class
        // in the main() method
        GFG g = new GFG();

        // iterating using nested for loop to traverse over
        // matrix

        // Outer for loop
        for (a = 0; a <= k; a++) {

            // Inner loop 1
            for (b = 0; b <= k - a; b++) {

                // Print white space for left spacing
                System.out.print(" ");
            }

            // Inner loop 2
            for (b = 0; b <= a; b++) {

                // nCr formula
                System.out.print(
                    " "
                    + g.factorial(a)
                          / (g.factorial(a - b)
                             * g.factorial(b)));
            }

            // By now, we are done with one row so
            // a new line
            System.out.println();
        }
    }
}
```

**Output**

```java
      1
     1 1
    1 2 1
   1 3 3 1
  1 4 6 4 1
```

**方法 2:** 使用二项式系数

行号*行*中的第‘A’项是二项式系数 *C(行，a)* ，所有行都以值 1 开始。想法是用 C(线，a-1)计算 C(线，a)。

```java
C(line, i) = C(line, i-1) * (line - i + 1) / i
```

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Print Pascal's Triangle

// Importing input output classes
import java.io.*;

// Main Class
public class GFG {

    // Method 1
    // Pascal function
    public static void printPascal(int k)
    {
        for (int line = 1; line <= k; line++) {
            for (int b = 0; b <= k - line; b++) {

                // Print whitespace for left spacing
                System.out.print(" ");
            }

            // Variable used to represent C(line, i)
            int C = 1;

            for (int a = 1; a <= line; a++) {

                // The first value in a line is always 1
                System.out.print(C + " ");

                C = C * (line - a) / a;
            }

            // By now, we are done with one row so
            // a new line is required
            System.out.println();
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Declare and initialize variable number
        // upto which Pascal's triangle is  required on
        // console
        int n = 6;

        // Calling the Pascal function(Method 1)
        printPascal(n);
    }
}
```

**Output**

```java
      1 
     1 1 
    1 2 1 
   1 3 3 1 
  1 4 6 4 1 
 1 5 10 10 5 1 
```