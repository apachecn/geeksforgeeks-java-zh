# bigentermath divide()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/bigintermath-divide-function-guava-Java/](https://www.geeksforgeeks.org/bigintegermath-divide-function-guava-java/)

[番石榴的 BigIntegerMath 类](https://www.geeksforgeeks.org/bigintegermath-class-guava-java/)的方法**除(bigintermate p，bigintermate q，舍入模式)**返回 p 除以 q 的结果，使用指定的舍入模式进行舍入。

**语法:**

```java
public static BigInteger divide(BigInteger p,
                                BigInteger q,
                                RoundingMode mode)

```

**参数:**该方法取以下参数:

*   **p** : dividend of large integer
*   **q** : a large integer divisor.
*   **mode** : the rounding mode for calculating the division of P and Q.

**返回值:**此方法返回 p 除以 q 的结果，使用指定的舍入模式进行舍入。

**异常:**如果 q == 0，或者如果 mode ==不必要且 a 不是 b 的整数倍，则方法抛出 ***算术异常***

#### 枚举舍入模式

| 枚举常数 | 描述 |
| **【天花板】** | 舍入模式向正无穷大舍入。 |
| **DOWN** | 舍入模式为向零舍入。 |
| **FLOOR** | 舍入模式为向负无穷大舍入。 |
| **HALF _ DOWN** | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下舍入为 DOWN。 |
| **HALF _ EVEN** | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下，向偶数邻居舍入。 |
| **【HALF _ UP】** | 取整模式为向“最近邻居”取整，除非两个邻居等距，在这种情况下取整。 |
| **【不必要的】** | 舍入模式断言请求的操作有确切的结果，因此没有舍入的必要。 |
| **UP** | 取整模式为远离零取整。 |

以下示例说明了 BigIntegerMath.divide()方法:

**例 1:**

```java
// Java code to show implementation of
// divide(BigInteger p, BigInteger q, RoundingMode mode)
// method of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        BigInteger dividend1 = BigInteger.valueOf(55);
        BigInteger divisor1 = BigInteger.valueOf(10);

        // Using divide()
        // method of Guava's BigIntegerMath class
        BigInteger
            quotient1
            = BigIntegerMath
                  .divide(dividend1,
                          divisor1,
                          RoundingMode.HALF_DOWN);

        System.out.println(dividend1 + " divided by "
                           + divisor1
                           + " with HALF_DOWN rounding mode: "
                           + quotient1);

        BigInteger dividend2 = BigInteger.valueOf(55);
        BigInteger divisor2 = BigInteger.valueOf(10);

        // Using divide()
        // method of Guava's BigIntegerMath class
        BigInteger
            quotient2
            = BigIntegerMath
                  .divide(dividend2,
                          divisor2,
                          RoundingMode.CEILING);

        System.out.println(dividend2 + " divided by "
                           + divisor2
                           + " with CEILING rounding mode: "
                           + quotient2);
    }
}
```

**输出:**

```java
55 divided by 10 with HALF_DOWN rounding mode: 5
55 divided by 10 with CEILING rounding mode: 6

```

**例 2:**

```java
// Java code to show implementation of
// divide(BigInteger p, BigInteger q, RoundingMode mode)
// method of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {

        try {

            BigInteger dividend1 = BigInteger.valueOf(25);
            BigInteger divisor1 = BigInteger.valueOf(0);

            // Using divide()
            // method of Guava's BigIntegerMath class
            // This should raise "ArithmeticException"
            // as divisor1 = 0
            BigInteger
                quotient1
                = BigIntegerMath
                      .divide(dividend1,
                              divisor1,
                              RoundingMode.HALF_DOWN);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.ArithmeticException: / by zero

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/math/bigintermath . html # divide-Java . math . biginger-Java . math . biginger-Java . math . roundingmode-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#divide-java.math.BigInteger-java.math.BigInteger-java.math.RoundingMode-)