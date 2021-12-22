# long math 类的 Java 番石榴| log2(long x，RoundingMode 模式)带示例

> 原文:[https://www . geesforgeks . org/Java-guava-log2 long-x-rounding mode-of-long math-class-with-examples/](https://www.geeksforgeeks.org/java-guava-log2long-x-roundingmode-mode-of-longmath-class-with-examples/)

番石榴[龙数学类](https://www.geeksforgeeks.org/longmath-class-guava-java/)的方法 **log2(长 x，四舍五入模式)**接受两个参数，根据第二个参数指定的四舍五入模式计算第一个参数四舍五入后的基数-2 对数值。

**语法:**

```
public static int log2(long x, RoundingMode mode)

```

**参数:**该方法取 2 个参数，其中 *x* 为长，*模式*为指定取整模式。

**返回值:**该方法返回 x 的以 2 为底的对数，根据指定的舍入方式进行舍入。

**异常:**此方法抛出以下参数:

*   **非法引数例外:**<= 0。
*   **Arithmetic exception:** If the mode is circular mode. No need, x is not a power of 2.

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

下面的例子说明了番石榴 LongMath 的 log2()方法的实现:

**例 1 :**

```
// Java code to show implementation of
// log2(long x, RoundingMode mode) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long n1 = 1111;

        // Using log2(long x, RoundingMode mode)
        // method of Guava's LongMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the "nearest neighbor" unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        System.out.println(LongMath.log2(
            n1,
            RoundingMode.HALF_EVEN));

        long n2 = 205;

        // Using log2(long x, RoundingMode mode)
        // method of Guava's LongMath class
        // The RoundingMode HALF_DOWN rounds towards
        // "nearest neighbor" unless both neighbors
        // are equidistant, in which case round down.
        System.out.println(LongMath.log2(
            n2,
            RoundingMode.HALF_DOWN));
    }
}
```

**输出:**

```
10
8

```

**例 2:**

```
// Java code to show implementation of
// log2(long x, RoundingMode mode) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static long findlog2(long x, RoundingMode mode)
    {
        try {
            // Using log2(long x, RoundingMode mode)
            // method of Guava's LongMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the "nearest neighbor" unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.
            // This should throw "IllegalArgumentException"
            // as x <= 0
            long ans = LongMath.log2(x, mode);

            // Return the answer
            return ans;
        }
        catch (Exception e) {
            System.out.println(e);
            return -1;
        }
    }

    // Driver code
    public static void main(String args[])
    {
        long x = -122;

        try {

            // Function calling
            findlog2(x, RoundingMode.HALF_EVEN);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.lang.IllegalArgumentException: x (-122) must be > 0

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/longmath . html # log2-long-Java . math . round ingmode-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#log2-long-java.math.RoundingMode-)