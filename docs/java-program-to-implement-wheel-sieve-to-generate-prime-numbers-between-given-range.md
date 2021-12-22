# Java 程序实现轮筛生成给定范围内的素数

> 原文:[https://www . geesforgeks . org/Java-程序到实现-轮筛-生成-质数-给定区间/](https://www.geeksforgeeks.org/java-program-to-implement-wheel-sieve-to-generate-prime-numbers-between-given-range/)

A [质数](https://www.geeksforgeeks.org/prime-numbers/)是大于 1 的整数，只能被 1 和自身整除。前几个质数是 2 3 5 7 11 13 17 19 23。给定一个范围， **L** 到 **R，**的任务是生成该范围内存在的所有素数。

**示例**

```
Input: 1 10
Output 2 3 5 7

Input: 20 30 
Output: 23 29
```

**方法 1:** 检查每个元素是否是素数。

*   在左到右的范围内迭代
*   检查每个元素是否是质数
*   打印范围内的质数

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Implement wheel Sieve to Generate Prime
// Numbers Between Given Range

import java.io.*;

class GFG {
    static boolean checkPrime(int n)
    {
        // Handling the edge case
        if (n == 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(n); ++i) {

            // checking the prime number
            if (n % i == 0) {
                return false;
            }
        }

        return true;
    }
    public static void main(String[] args)
    {
        // starting in a range
        int L = 1;

        // ending in a range
        int R = 20;

        for (int i = L; i <= R; ++i) {

            // printing the prime number
            if (checkPrime(i) == true) {
                System.out.print(i + " ");
            }
        }
    }
}
```

**Output**

```
2 3 5 7 11 13 17 19
```

*   **时间复杂度** : O(n * sqrt(n))
*   **空间复杂度** : O(1)

**方法 2:** 使用厄拉多塞[筛](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)生成所有素数

*   使用厄拉多塞筛生成所有素数(参考[这篇](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)文章)
*   标记所有素数的所有倍数，剩下的数是左素数
*   直到值的最大范围
*   打印给定范围内的所有质数

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Implement wheel Sieve to Generate Prime
// Numbers Between Given Range

import java.io.*;

class GFG {

    // Maximum range
    static boolean max[] = new boolean[1000001];
    static void fill()
    {
        // Maximum Range
        int n = 1000000;

        // Mark all numbers as a prime
        for (int i = 2; i <= n; ++i) {
            max[i] = true;
        }
        for (int i = 2; i <= Math.sqrt(n); ++i) {

            // if number is prime
            if (max[i] == true) {

                // mark all the factors
                // of i non prime
                for (int j = i * i; j <= n; j += i) {
                    max[j] = false;
                }
            }
        }
    }

    static void range(int L, int R)
    {
        for (int i = L; i <= R; ++i) {

            // checking the prime number
            if (max[i] == true) {
                // print the prime number
                System.out.print(i + " ");
            }
        }
    }
    public static void main(String[] args)
    {
        // starting in a range
        int L = 20;

        // ending in a range
        int R = 40;

        // mark all the numbers
        fill();

        // printing the prime numbers in range
        range(L, R);
    }
}
```

**Output**

```
23 29 31 37
```

*   **时间复杂度:** [O(nlog(logn)](https://www.geeksforgeeks.org/how-is-the-time-complexity-of-sieve-of-eratosthenes-is-nloglogn/)
*   **空间复杂度:** O(1)

**方法 3:** 用轮筛生成所有素数。这种方法比上面讨论的方法优化得多。在这种方法中，我们使用[轮因式分解](https://www.geeksforgeeks.org/wheel-factorization-algorithm/)方法来寻找给定范围内的素数。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check if the
// given number is prime using
// Wheel Factorization Method

import java.util.*;

class GFG {

    // Function to check if a given
    // number x is prime or not
    static boolean isPrime(int N)
    {
        boolean isPrime = true;

        // The Wheel for checking
        // prime number
        int[] arr = { 7, 11, 13, 17, 19, 23, 29, 31 };

        // Base Case
        if (N < 2) {
            isPrime = false;
        }

        // Check for the number taken
        // as basis
        if (N % 2 == 0 || N % 3 == 0 || N % 5 == 0) {
            isPrime = false;
        }

        // Check for Wheel
        // Here i, acts as the layer
        // of the wheel
        for (int i = 0; i < Math.sqrt(N); i += 30) {

            // Check for the list of
            // Sieve in arr[]
            for (int c : arr) {

                // If number is greater
                // than sqrt(N) break
                if (c > Math.sqrt(N)) {
                    break;
                }

                // Check if N is a multiple
                // of prime number in the
                // wheel
                else {
                    if (N % (c + i) == 0) {
                        isPrime = false;
                        break;
                    }
                }

                // If at any iteration
                // isPrime is false,
                // break from the loop
                if (!isPrime)
                    break;
            }
        }

        if (isPrime)
            return true;
        else
            return false;
    }

    // Driver's Code
    public static void main(String args[])
    {

        // Range
        int L = 10;
        int R = 20;
        for (int i = L; i <= R; ++i) {

            // Function call for primality
            // check

            // if true
            if (isPrime(i) == true) {

                // print the prime number
                System.out.print(i + " ");
            }
        }
    }
}
```

**Output**

```
11 13 17 19
```