# 用二分搜索法求一个数的平方根的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-使用二进制搜索来查找数字的平方根/](https://www.geeksforgeeks.org/java-program-to-find-the-square-root-of-a-number-using-binary-search/)

给定一个非负数，使用[二分搜索法](https://www.geeksforgeeks.org/binary-search/)方法求一个数的平方根。

**例:**

```java
Input: x = 16
Output: 4
Explanation:  The square root of 16 is 4.

Input: x = 5
Output: 2
Explanation:  The square root of 5 lies in between
2 and 3 so floor of the square root is 2.
```

**天真方法:**

*   Check the square of each element until n, and store the answer until the square is less than or equal to n.

## Java

```java
// Java program to Find the square root of given numbers
// by brute force technique

import java.io.*;

class GFG {
    static int cuberoot(int n)
    {
        int ans = 0;

        for (int i = 1; i <= n; ++i) {

            // checking every number cube
            if (i * i <= n) {
                ans = i;
            }
        }
        return ans;
    }
    public static void main(String[] args)
    {
        // Number
        int number = 16;

        // Checking number
        int cuberoot = cuberoot(number);
        System.out.println(cuberoot);
    }
}
```

**输出**

```java
4

```