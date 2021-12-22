# Java 番石榴| IntMath.divide(int，int，RoundingMode)方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-int math-divideint-int-rounding mode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-intmath-divideint-int-roundingmode-method-with-examples/)

番石榴 [IntMath Class](https://www.geeksforgeeks.org/intmath-class-guava-java/) 的**除法(int p，int q，rounding mode)**方法接受三个参数，计算第一个参数除以第二个参数的结果，根据第三个参数指定的舍入方式进行舍入。

**语法:**

```java
public static int divide(int p,
                          int q,
                          RoundingMode mode)

```

**参数:**该方法取 3 个参数，其中***p******q***为 ints， ***模式*** 为指定取整模式。

**返回值:**该方法返回第一个参数除以第二个参数，根据第三个参数指定的舍入方式进行舍入。

**异常:**方法抛出 ***算法异常*** 如果:

*   q == 0，或
*   mode = =，p 不是 q 的整数倍。

#### 枚举舍入模式

| 枚举常数 | 描述 |
| **天花板** | 舍入模式，向正无穷大舍入。 |
| **下降** | 舍入模式，向零舍入。 |
| **地板** | 舍入模式，向负无穷大舍入。 |
| **半降** | 舍入模式向“最近的邻居”舍入，除非两个邻居等距，在这种情况下向下舍入。 |
| **HALF_EVEN** | 舍入模式向“最近的邻居”舍入，除非两个邻居等距，在这种情况下，向偶数邻居舍入。 |
| **半开** | 舍入模式向“最近的邻居”舍入，除非两个邻居等距，在这种情况下舍入。 |
| **不必要的** | 舍入模式来断言所请求的操作具有精确的结果，因此不需要舍入。 |
| **上升** | 舍入模式从零开始舍入。 |

下面的例子说明了上述方法的实现:

**例 1 :**

```java
// Java code to show implementation of
// divide(int p, int q, RoundingMode mode)
// method of Guava's IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int dividend1 = 55;
        int divisor1 = 10;

        // Using divide(int p, int q,
        // RoundingMode mode)
        // method of Guava's IntMath class
        int quotient1
            = IntMath.divide(dividend1, divisor1,
                             RoundingMode.HALF_DOWN);

        System.out.println(quotient1);

        int dividend2 = 55;
        int divisor2 = 10;

        // Using divide(int p, int q,
        // RoundingMode mode)
        // method of Guava's IntMath class
        int quotient2
            = IntMath.divide(dividend2, divisor2,
                             RoundingMode.CEILING);

        System.out.println(quotient2);
    }
}
```

**Output:**

```java
5
6

```

**例 2 :**

```java
// Java code to show implementation of
// divide(int p, int q, RoundingMode mode)
// method of Guava's IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findDiv(int dividend,
                       int divisor,
                       RoundingMode mode)
    {
        try {
            // Using divide(int p, int q,
            // RoundingMode mode)
            // method of Guava's IntMath class
            int quotient
                = IntMath.divide(dividend,
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
        int dividend = 32;
        int divisor = 0;

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

**Output:**

```java
java.lang.ArithmeticException: / by zero

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # divide-int-int-Java . math . round ingmode-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#divide-int-int-java.math.RoundingMode-)