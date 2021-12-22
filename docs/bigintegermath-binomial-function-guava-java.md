# bigentermath 二项式()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/bigintermath-binomial-function-guava-Java/](https://www.geeksforgeeks.org/bigintegermath-binomial-function-guava-java/)

**番石榴的 BigIntegerMath 类的二项式(int n，int k)** 方法返回 ***n 选择 k*** ，也称为 n 和 k 的 ***二项式系数*** ，即

```java
n! / (k! (n - k)!)
```

**语法:**

```java
public static BigInteger binomial(int n, int k)

```

**参数:**该方法取以下参数:

*   **n** : Cardinality of binomial expansion.
*   **k** : the power of binomial expansion.

**返回值:**该方法返回 n 和 k 的二项式系数。

**异常:**如果 n < 0，k < 0 或 k > n，此方法抛出*T3 异常*

**注意:**结果可以占用多达 O(k log n)的空间。

以下示例说明了 BigIntegerMath.binomial()方法:

**例 1:**

```java
// Java code to show implementation of
// binomial(int n, int k) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int n = 5;
        int k = 2;

        // Using binomial(int n, int k) method of
        // Guava's BigIntegerMath class
        BigInteger ans = BigIntegerMath.binomial(n, k);

        System.out.println("Binomial Coefficient of "
                           + n + " & " + k
                           + " is: " + ans);

        int n1 = 15;
        int k1 = 9;

        // Using binomial(int n, int k) method of
        // Guava's BigIntegerMath class
        BigInteger ans1 = BigIntegerMath.binomial(n1, k1);

        System.out.println("Binomial Coefficient of "
                           + n1 + " & " + k1
                           + " is: " + ans1);
    }
}
```

**输出:**

```java
Binomial Coefficient of 5 & 2 is: 10
Binomial Coefficient of 15 & 9 is: 5005

```

**例 2:**

```java
// Java code to show implementation of
// binomial(int n, int k) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {

        try {
            int n = 5;
            int k = 7;

            // Using binomial(int n, int k) method of
            // Guava's BigIntegerMath class
            // This should raise "IllegalArgumentException"
            // as k > n
            BigInteger ans = BigIntegerMath.binomial(n, k);

            System.out.println("Binomial Coefficient of"
                               + n + " & " + k
                               + " is: " + ans);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.IllegalArgumentException: k (7) > n (5)

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/math/bigentermath . html # binomial-int-int-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#binomial-int-int-)