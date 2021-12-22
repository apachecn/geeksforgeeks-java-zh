# 爪哇番石榴| LongMath.divide(长、长、圆模式)方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-long math-dividelong-long-rounding-mode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longmath-dividelong-long-roundingmode-method-with-examples/)

番石榴[龙数学类](https://www.geeksforgeeks.org/longmath-class-guava-java/)的**除法(长 p，长 q，舍入模式)**方法接受三个参数，计算第一个参数除以第二个参数的结果，根据第三个参数指定的舍入模式进行舍入。

**语法:**

```java
public static long divide(long p,
                          long q,
                          RoundingMode mode)

```

**参数:**该方法取 3 个参数，其中 ***p*** 和 ***q*** 为长整型， ***模式*** 为指定的舍入模式。

**返回值:**该方法返回第一个参数除以第二个参数，根据第三个参数指定的舍入方式进行舍入。

**异常:**方法抛出 ***算法异常*** 如果:

*   Q == 0, or
*   Pattern = = unnecessary and p is not an integer multiple of Q.

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

下面的例子说明了上述方法的实现:

**例 1 :**

```java
// Java code to show implementation of
// divide(long p, long q, RoundingMode mode)
// method of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long dividend1 = 55;
        long divisor1 = 10;

        // Using divide(long p, long q,
        // RoundingMode mode)
        // method of Guava's LongMath class
        long quotient1
            = LongMath.divide(dividend1, divisor1,
                              RoundingMode.HALF_DOWN);

        System.out.println(quotient1);

        long dividend2 = 55;
        long divisor2 = 10;

        // Using divide(long p, long q,
        // RoundingMode mode)
        // method of Guava's LongMath class
        long quotient2
            = LongMath.divide(dividend2, divisor2,
                              RoundingMode.CEILING);

        System.out.println(quotient2);
    }
}
```

**输出:**

```java
5
6

```

**例 2 :**

```java
// Java code to show implementation of
// divide(long p, long q, RoundingMode mode)
// method of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static long findDiv(long dividend,
                        long divisor,
                        RoundingMode mode)
    {
        try {
            // Using divide(long p, long q,
            // RoundingMode mode)
            // method of Guava's LongMath class
            long quotient
                = LongMath.divide(dividend,
                                  divisor,
                                  RoundingMode.HALF_DOWN);

            // Return the answer
            return quotient;
        }
        catch (Exception e) {
            System.out.println(e);
            return -1;
        }
    }

    // Driver code
    public static void main(String args[])
    {
        long dividend = 32;
        long divisor = 0;

        try {

            // Function calling
            findDiv(dividend, divisor,
                    RoundingMode.HALF_EVEN);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.ArithmeticException: / by zero

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/longmath . html # divide-long-long-Java . math . round ingmode-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#divide-long-long-java.math.RoundingMode-)