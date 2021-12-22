# bigentermath sqrt()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/bigintermath-sqrt-function-guava-Java/](https://www.geeksforgeeks.org/bigintegermath-sqrt-function-guava-java/)

[番石榴的大整数类](https://www.geeksforgeeks.org/bigintegermath-class-guava-java/)的方法 **sqrt(大整数 x，舍入模式)**返回 x 的**平方根**，用指定的舍入模式进行舍入。

**语法:**

```
public static BigInteger sqrt(BigInteger x, RoundingMode mode)

```

**参数:**该方法取以下参数:

*   **×** : A large integer for square root.
*   **Mode** : The rounding mode for calculating the square root.

**返回值:**该方法返回 x 的**平方根**，用指定的舍入方式进行舍入。

**异常:**此方法抛出以下异常:

*   **IllegalArgumentException:**if x<0 .
*   **Arithmetic exception:** If the mode is circular mode. No, sqrt(x) is not an integer.

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

以下示例说明了 BigIntegerMath.sqrt()方法:

**例 1:**

```
// Java code to show implementation of
// sqrt(BigInteger x, RoundingMode mode) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        BigInteger x1 = BigInteger.valueOf(226);

        // Using sqrt(BigInteger x, RoundingMode mode)
        // method of Guava's BigIntegerMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the nearest neighbor unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        BigInteger ans1 = BigIntegerMath
                              .sqrt(x1,
                                    RoundingMode.HALF_EVEN);

        System.out.println("Square root of " + x1
                           + "with HALF_EVEN rounding mode is: "
                           + ans1);

        BigInteger x2 = BigInteger.valueOf(154);

        // Using sqrt(BigInteger x, RoundingMode mode)
        // method of Guava's BigIntegerMath class
        // The RoundingMode FLOOR rounds towards
        // negative infinity.
        BigInteger ans2 = BigIntegerMath
                              .sqrt(x2,
                                    RoundingMode.FLOOR);

        System.out.println("Square root of " + x2
                           + "with FLOOR rounding mode is: "
                           + ans2);
    }
}
```

**输出:**

```
Square root of 226with HALF_EVEN rounding mode is: 15
Square root of 154with FLOOR rounding mode is: 12

```

**例 2:**

```
// Java code to show implementation of
// sqrt(BigInteger x, RoundingMode mode) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {

        try {
            BigInteger x1 = BigInteger.valueOf(-65);

            // Using sqrt(BigInteger x, RoundingMode mode)
            // method of Guava's BigIntegerMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the nearest neighbor unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.
            BigInteger ans1 = BigIntegerMath
                                  .sqrt(x1,
                                        RoundingMode.HALF_EVEN);

            // This should throw "IllegalArgumentException"
            // as x1 < 0
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Exception: java.lang.IllegalArgumentException: x (-65) must be >= 0

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/math/bigintermath . html # sqrt-Java . math . biginger-Java . math . round ingmode-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#sqrt-java.math.BigInteger-java.math.RoundingMode-)