# 实现厄拉多塞筛在给定范围内生成素数的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序-实现-筛选-生成-给定范围之间的素数/](https://www.geeksforgeeks.org/java-program-to-implement-sieve-of-eratosthenes-to-generate-prime-numbers-between-given-range/)

一个能被 1 整除的数，或者一个因子为 1 的数，其本身称为质数。当 n 小于 1000 万左右时，厄拉多塞筛是寻找所有小于 n 的素数的最有效方法之一。

**例:**

```
Input : from = 1, to = 20
Output: 2 3 5 7 11 13 17 19

Input : from = 4, to = 15
Output: 5 7 11 13
```

**A .天真的方法:**

1.  Define a function called isprime(int n), which will check whether a number is prime.
2.  Cycle from "from" to "to".
3.  Internal loop, check whether I is prime, and then print the value of I.

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Generate Prime
// Numbers Between Given Range
class GFG {
    public static boolean isprime(int n)
    {
        if (n == 1)
            return false;

        for (int i = 2; i <= Math.sqrt(n); i++)

            // Check if a number has factors
            // its not prime and return 0
            if (n % i == 0)
                return false;

        // Check if a number dont
        // have any factore
        // its prime and return 1
        return true;
    }
    public static void main(String[] args)
    {

        // Suppose we want to print
        // prime no.  from 1 to 20
        int from = 1, to = 20, k = 0;
        for (int i = from; i <= to; i++)
            if (isprime(i))
                System.out.print(" " + i);
    }
}
```

**Output**

```
 2 3 5 7 11 13 17 19
```

**时间复杂度:** O(n <sup>3/2</sup>

**b .**筛 T2】厄拉多塞:

最初，假设从 0 到 n 的每个数字都是质数，将每个数字的数组值指定为 1。然后，通过将数组中的值从 1 更改为 0 来删除每个非质数，最后，只打印数组值为 1 的那些数，即质数。

**方法:**

1.  Slave user
2.  Enter n in the array, and fill in 1 corresponding to each element.
3.  Be a [0]=0 and a [1]=0 because we know that 0,1 is not a prime number.
4.  Assuming that the first number (2) is a prime number, remove the multiple of 2 (because the multiple of 2 will be a non-prime number)
5.  Continue step 3 until the square root (n)
6.  Print with non-strikethrough (or

下面是上述方法的实现:

T3】JavaT5

```
// Java Program to Implement
// Sieve of eratosthenes
// to Generate Prime Numbers
// Between Given Range
import java.util.*;
class GFG {

    public static void main(String[] args)
    {
        int from = 1, to = 20, i;
        boolean[] a = new boolean[to + 1];
        Arrays.fill(a, true);

        // 0 and 1 are not prime
        a[0] = false;
        a[1] = false;
        for (i = 2; i <= Math.sqrt(to); i++)

            // Check if number is prime
            if (a[i])
                for (int j = i * i; j <= to; j += i) {
                    a[j] = false;
                }
        for (i = from; i <= to; i++) {

            // Printing only prime numbers
            if (a[i])
                System.out.print(" " + i);
        }
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(n log(log n))