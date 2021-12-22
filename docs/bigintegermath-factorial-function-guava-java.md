# bigentermath 阶乘()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/bigintermath-factorial-function-guava-Java/](https://www.geeksforgeeks.org/bigintegermath-factorial-function-guava-java/)

[番石榴的 BigIntegerMath 类](https://www.geeksforgeeks.org/bigintegermath-class-guava-java/)的方法**阶乘(int n)** 被用来寻找给定数的阶乘。它返回 n！，即前 n 个正整数的乘积。
**语法:**

```java
public static BigInteger factorial(int n)
```

**参数:**该方法以数字 **n** 为要求阶乘的参数。
**返回值:**此方法返回给定数字 n 的阶乘。
**异常:**如果 n < 0，此方法抛出***IllegalArgumentException***。
**注:**

*   如果 n == 0，则该方法返回 1。
*   结果占用 O(n log n)空间，谨慎使用。
*   这使用有效的二进制递归算法来计算具有平衡乘法的阶乘。

以下示例说明了 BigIntegerMath.factorial()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show implementation of
// factorial() method of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int n1 = 10;

        // Using factorial(int n) method of
        // Guava's BigIntegerMath class
        BigInteger ans1 = BigIntegerMath.factorial(n1);

        System.out.println("Factorial of " + n1
                           + " is: " + ans1);

        int n2 = 12;

        // Using factorial(int n) method of
        // Guava's BigIntegerMath class
        BigInteger ans2 = BigIntegerMath.factorial(n2);

        System.out.println("Factorial of " + n2
                           + " is: " + ans2);
    }
}
```

**Output:** 

```java
Factorial of 10 is: 3628800
Factorial of 12 is: 479001600
```