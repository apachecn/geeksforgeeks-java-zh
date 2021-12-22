# Java 程序求数列 1/1 的和！+ 2/2!+ 3/3!+ ……1/N！

> 原文:[https://www . geesforgeks . org/Java-program-to-find-sum-series-1-1-2-2-3-3-1-n/](https://www.geeksforgeeks.org/java-program-to-find-sum-of-the-series-1-1-2-2-3-3-1-n/)

一个数的阶乘简单地返回该数与所有小于 1 的数的乘积，对该数应用阶乘。现在问题来了，级数是收敛的还是发散的。根据数学中[无穷级数](https://www.geeksforgeeks.org/efficient-program-compute-sum-series-11-12-13-14-1n/)和[阶乘](https://www.geeksforgeeks.org/program-for-factorial-of-a-number/)的概念，级数不一定收敛，但可以包含一个收敛的子序列。

**插图:**

> n！= n *(n-1)×(n-2)×(n-3)×(n-4)×……××4×3×2×1

```
Input      : n = 5
Processing : 1/1! + 2/2! + 3/3! + 4/4! + 5/5!
             1    + 2/2  + 3/6  + 4/24 + 5/120
Output     : 2.708333333333333            
```

**进场:**

*   输入术语数 n
*   创建一个函数来计算数列的和，比如，计算总和。
*   在 calculateSum 函数()中，创建一个变量 Sum，用于存储序列的总和。
*   循环运行 N 次。
*   调用阶乘函数()计算给定数字的阶乘。
*   返回总和。

**实现:**

T5】Java

```
// Java Program to Find Sum of the Series
// 1/1! + 2/2! + 3/3! + ……1/N!

// Importing java generic libraries
import java.io.*;

class GFG {

    // Function(recursive) to calculate factorial
    public static double factorial(int i)
    {
        // Step1: Base case
        if (i == 1) {
            return 1;
        }
        // Step2&3: Recursion execution & call statements
        return i * factorial(i - 1);
    }

    // Fuction to calculate sum of series
    public static double calculateSum(int N)
    {
        // Store total_sum in sum
        double sum = 0;

        // Iteration by running a loop N times
        for (int i = 1; i <= N; i++) {
            sum = sum + ((double)i / factorial(i));
        }

        // Return calculated final sum
        return sum;
    }

    // Main driver method
    public static void main(String[] args)
    {
        /* No of terms in series
           taken inn order to show output */
        int N = 5;

        // Print sum of series by
        // calling function calculating sum of series
        System.out.println("The sum of series upto " + N
                           + " terms is : "
                           + calculateSum(N));
    }
}
```

**输出**

```
The sum of series upto 5 terms is : 2.708333333333333
```

**时间复杂度:** O(n)