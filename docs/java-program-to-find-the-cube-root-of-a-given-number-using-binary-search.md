# 利用二分搜索法求给定数立方根的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-给定数字的立方根-使用二进制搜索/](https://www.geeksforgeeks.org/java-program-to-find-the-cube-root-of-a-given-number-using-binary-search/)

给定一个非负数，使用[二分搜索法](https://www.geeksforgeeks.org/binary-search/)方法求一个数的立方根。

**例:**

```java
Input: x = 27
Output: 3
Explanation:  The cube root of 16 is 4.

Input: x = 120
Output: 4
Explanation:  The cube root of 120 lies in between
4 and 5 so floor of the cube root is 4.
```

**天真方法:**

*   Check the cube of each element until n, and store the answer until the cube is less than or equal to n.

## Java

```java
// Java Program to Find the cube root
// of given number using Naive approach
import java.io.*;
class GFG {
    static int cuberoot(int n)
    {
        int ans = 0;

        for (int i = 1; i <= n; ++i) {
            // checking every number cube
            if (i * i * i <= n) {
                ans = i;
            }
        }
        return ans;
    }
    public static void main(String[] args)
    {
        // Number
        int number = 27;
        // Checking number
        int cuberoot = cuberoot(number);
        System.out.println(cuberoot);
    }
}
```

**输出**

```java
3

```