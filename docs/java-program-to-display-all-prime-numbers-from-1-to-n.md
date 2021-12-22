# 显示从 1 到 N 的所有质数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-display-all-prime-numbers-from-1-n/](https://www.geeksforgeeks.org/java-program-to-display-all-prime-numbers-from-1-to-n/)

对于给定的数 N，目的是找出从 1 到 N 的所有素数。

**示例:**

```
Input: N = 11
Output: 2, 3, 5, 7, 11
```

```
Input: N = 7
Output: 2, 3, 5, 7 
```

**方法 1:**

*   首先，考虑给定的数字 N 作为输入。
*   然后应用 for 循环来迭代从 1 到 n 的数字
*   最后，检查每个数字是否是质数，如果是质数，然后用暴力打印。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to find all the
// prime numbers from 1 to N
class gfg {

    // Function to print all the
    // prime numbers till N
    static void prime_N(int N)
    {
        // Declaring the variables
        int x, y, flg;

        // Printing display message
        System.out.println(
            "All the Prime numbers within 1 and " + N
            + " are:");

        // Using for loop for traversing all
        // the numbers from 1 to N
        for (x = 1; x <= N; x++) {

            // Omit 0 and 1 as they are
            // neither prime nor composite
            if (x == 1 || x == 0)
                continue;

            // Using flag variable to check
            // if x is prime or not
            flg = 1;

            for (y = 2; y <= x / 2; ++y) {
                if (x % y == 0) {
                    flg = 0;
                    break;
                }
            }

            // If flag is 1 then x is prime but
            // if flag is 0 then x is not prime
            if (flg == 1)
                System.out.print(x + " ");
        }
    }

    // The Driver code
    public static void main(String[] args)
    {
        int N = 45;

        prime_N(N);
    }
}
```

**Output**

```
All the Prime numbers within 1 and 45 are:
2 3 5 7 11 13 17 19 23 29 31 37 41 43 
```

**时间复杂度:** O(N <sup>2</sup> )

**方法 2:**

*   首先，考虑给定的数字 N 作为输入。
*   然后应用 for 循环来迭代从 1 到 n 的数字
*   最后，检查每个数字是否是质数，如果是质数，用平方根法打印出来。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to find all the
// prime numbers from 1 to N
class gfg {

    // Function to print all the
    // prime numbers till N
    static void prime_N(int N)
    {
        // Declaring the variables
        int x, y, flg;

        // Printing display message
        System.out.println(
            "All the Prime numbers within 1 and " + N
            + " are:");

        // Using for loop for traversing all
        // the numbers from 1 to N
        for (x = 2; x <= N; x++) {

            // Using flag variable to check
            // if x is prime or not
            flg = 1;

            for (y = 2; y * y <= x; y++) {
                if (x % y == 0) {
                    flg = 0;
                    break;
                }
            }

            // If flag is 1 then x is prime but
            // if flag is 0 then x is not prime
            if (flg == 1)
                System.out.print(x + " ");
        }
    }

    // The Driver code
    public static void main(String[] args)
    {
        int N = 45;

        prime_N(N);
    }
}
```

**Output**

```
All the Prime numbers within 1 and 45 are:
2 3 5 7 11 13 17 19 23 29 31 37 41 43 
```