# 执行给定数字唯一因子分解的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序执行给定数字的唯一因子分解/](https://www.geeksforgeeks.org/java-program-to-perform-the-unique-factorization-of-a-given-number/)

给定一个数字 **n** ，任务是编写一个高效的程序来打印 n 的所有唯一质因数。

**例**

```
Input: 12
Output: 2, 3
Explanation: All prime factors or 12 are 2, 2, 3\. In those factors, unique factors
         are 2 and 3.

Input: 315 
Output: 3, 5, 7
```

**寻找所有质因数的步骤**

**1)** 当 n 可被 2 整除时，打印 2，将 n 除以 2。

**2)** 第 1 步后，n 必须为奇数。现在开始一个从 i = 3 到 n 的平方根的循环，当我除 n 时，打印 I，用 I 除 n，将 I 增加 2，然后继续。

**3)** 如果 n 是素数且大于 2，那么通过以上两步 n 不会变成 1。所以如果大于 2 就打印 n。

在第二步中，循环运行到 n 的平方根，因为只有当一个数小于或大于 n 的平方根，第二个数大于或等于 n 的平方根时，第 n 个数的乘积的对才有可能。

例如，假设 n =16，16 的平方根是 4，16 的因子是 1×16，16×1，2×8，8×2，4×4 在这个序列中，第一个数应该小于或等于 n 的平方根，第二个数大于或等于 n 的平方根。

**数学证明:**

1.  让 x < sqrt(n)和 y < sqrt(n)乘以两个方程 x×y < n，因此当任何 x 和 y 小于 n 时，任何 x 和 y 的乘积总是小于 n
2.  让 x > sqrt(n)和 y > sqrt(n)乘以两个方程 x×y > n，因此当任何 x 和 y 小于 n 时，任何 x 和 y 的乘积总是小于 n
3.  假设一个数字低于 sqrt(n)，第二个数字高于 sqrt(n)。在这种情况下，总有至少一对数的乘积为 n，让 x 和 y 是乘积为 n 的两个数，我们可以写出 x = sqrt(n) * sqrt(n)/y 的第一个⇾方程

**有两个条件:**

*   当 y < sqrt(n) i.e 1 < sqrt(n)/y so we can write 1st equation  x = sqrt(n)*(1+b) hence x > sqrt(n)
*   当 y < sqrt(n) i.e 1 > sqrt(n)/y 时，我们可以写出第一个方程 x = sqrt(n)*(1-b)，因此 x < sqrt(n)。

因此，我们可以得出结论，对于 x*y=n，至少有一个数小于等于 sqrt(n)或大于等于 sqrt(n)

这个概念被用在许多数论算法中，如[筛](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)、[求 n 的所有因子](https://www.geeksforgeeks.org/find-divisors-natural-number-set-1/)、[T5】等](https://www.geeksforgeeks.org/find-divisors-natural-number-set-1/) 

### 寻找给定数的唯一[素因子](https://www.geeksforgeeks.org/prime-factor/)的方法

**1。使用 HashSet 的方法**

*   当 n 可被 2 整除时，将 2 存储在集合中，并将 n 除以 2。
*   经过以上步骤，n 一定是奇数。现在开始一个从 i = 3 到 n 的平方根的循环，当我除 n 的时候，把 I 存储在集合中，用 I 除 n，当我除 n 失败后，把 I 增加 2，继续。
*   如果 n 是一个质数并且大于 2，那么通过以上两步 n 不会变成 1。因此，如果大于 2，则存储在集合 n 中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to print all unique prime factors

import java.io.*;
import java.lang.Math;
import java.util.*;
class GFG {

    // A function to print all prime factors
    // of a given number n
    public static void primeFactors(int n,
                                    HashSet<Integer> h)
    {
        // Print the number of 2s that divide n
        while (n % 2 == 0) {

            h.add(2);
            n /= 2;
        }

        // n must be odd at this point. So we can
        // skip one element (Note i = i +2)
        for (int i = 3; i <= Math.sqrt(n); i += 2) {

            // While i divides n, print i and divide n
            while (n % i == 0) {
                h.add(i);
                n /= i;
            }
        }

        // This condition is to handle the case when
        // n is a prime number greater than 2
        if (n > 2)
            h.add(n);
    }
    static void printFactors(HashSet<Integer> H)
    {
        // Itearator over the HashSet
        Iterator<Integer> It = H.iterator();

        // printing the elements of HashSet
        while (It.hasNext()) {

            System.out.print(It.next() + " ");
        }
        System.out.println();
    }
    public static void main(String[] args)
    {
        int n = 15;
        HashSet<Integer> h = new HashSet<>();

        primeFactors(n, h);

        // print the unique factors
        printFactors(h);
    }
}
```

**Output**

```
3 5
```

**时间复杂度:** O(sqrt(n))

**2。使用筛子的方法:**

*   标记所有的倍数，直到上面提到的 sqrt(n)原因，其中 n 是数组的最大长度。
*   直到数组的长度，数组看起来像是 2 的倍数，依此类推。

<figure class="table">

| Zero | one | Two | three | Two |
| --- | --- | --- | --- | --- |

</figure>

*   标记所有数字的剩余倍数，直到 sqrt(n)。寻找第 n 个数的因子。
    *   用 n/dp[n]除 n，直到 dp[n]！=n
    *   将所有 dp[n]值存储在 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 或 [TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 中，最后将 n 存储在集合中。
    *   打印唯一因素集。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to print all unique prime factors

import java.util.*;
import java.io.*;

public class GFG {
    static int dp[] = new int[100001];

    static void fill()
    {
        int n = 100000;
        for (int i = 1; i <= n; ++i) {
            dp[i] = i;
        }

        // mark the multiply of 2
        for (int i = 2; i <= n; i += 2) {
            dp[i] = 2;
        }

        // mark the multilple of less than sqrt(n)
        for (int i = 3; i <= Math.sqrt(n); ++i) {
            for (int j = i * i; j <= n; j += i) {
                if (dp[j] == j) {
                    dp[j] = i;
                }
            }
        }
    }
    static void Factors(int n, HashSet<Integer> h)
    {

        // when n is prime number
        if (dp[n] == n) {
            h.add(n);
            return;
        }
        else {
            while (dp[n] != n) {

                // Adding the multiple.
                h.add(dp[n]);
                n = n / dp[n];
            }
            h.add(n);
            return;
        }
    }
    static void print(HashSet<Integer> h)
    {
        Iterator<Integer> it = h.iterator();

        // printing the elements
        while (it.hasNext()) {
            System.out.print(it.next() + " ");
        }
    }

    public static void main(String[] args)
    {
        int n = 21;
        fill();
        HashSet<Integer> h = new HashSet<>();

        // finding the factors
        Factors(n, h);
        print(h);
    }
}
```

**Output**

```
3 7
```

**时间复杂度:** O(logn)