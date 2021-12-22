# 爪哇番石榴| LongMath log10(长 x，圆模式)方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-long math-log10 long-x-rounding mode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longmath-log10long-x-roundingmode-mode-method-with-examples/)

番石榴[龙数学类](https://www.geeksforgeeks.org/longmath-class-guava-java/)的方法 **log10(长 x，四舍五入模式)**接受两个参数，根据第二个参数指定的四舍五入模式计算第一个参数四舍五入后的基数-10 对数值。

**语法:**

```java
public static int log10(long x, RoundingMode mode)

```

**参数:**该方法取 2 个参数:

*   ***x*** is the long value of the logarithm to be found.
*   ***mode*** is the specified rounding mode.

**返回值:**该方法返回 x 的以 10 为底的对数，根据指定的舍入方式进行舍入。

**异常:**此方法抛出以下参数:

*   **非法辩解例外:**x < 0′I′I′I′I′I′I。
*   **Arithmetic exception:** If the mode is circular mode. No need, x is not a power of ten.

#### 枚举舍入模式

| 枚举常数 | 描述 |
| --- | --- |
| **【天花板】** | 舍入模式向正无穷大舍入。 |
| **DOWN** | 舍入模式为向零舍入。 |
| **FLOOR** | 舍入模式为向负无穷大舍入。 |
| **HALF _ DOWN** | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下舍入为 DOWN。 |
| **HALF _ EVEN** | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下，向偶数邻居舍入。 |
| **【HALF _ UP】** | 取整模式为向“最近邻居”取整，除非两个邻居等距，在这种情况下取整。 |
| **【不必要的】** | 舍入模式断言请求的操作有确切的结果，因此没有舍入的必要。 |
| **UP** | 取整模式为远离零取整。 |

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```java
// Java code to show implementation of
// log10(long x, RoundingMode mode) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long a1 = 10000;

        // Using log10(long x, RoundingMode mode)
        // method of Guava's LongMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the "nearest neighbor" unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        System.out.println(
            LongMath.log10(
                a1,
                RoundingMode.HALF_EVEN));

        long a2 = 15;

        // Using log10(long x, RoundingMode mode)
        // method of Guava's LongMath class
        // The RoundingMode HALF_DOWN rounds towards
        // "nearest neighbor" unless both neighbors
        // are equidistant, in which case round down.
        System.out.println(
            LongMath.log10(a2,
                           RoundingMode.HALF_DOWN));
    }
}
```

输出:

```java
4
1

```

**例 2 :**

```java
// Java code to show implementation of
// log10(long x, RoundingMode mode) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static int findlog10(long x, RoundingMode mode)
    {
        try {
            // Using log10(long x, RoundingMode mode)
            // method of Guava's LongMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the "nearest neighbor" unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.
            // This should throw "IllegalArgumentException"
            // as x <= 0
            int ans = LongMath.log10(x, mode);

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
            findlog10(x, RoundingMode.HALF_EVEN);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

输出:

```java
java.lang.IllegalArgumentException: x (-122) must be > 0

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/long math . html # log10-long-Java . math . round ingmode-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#log10-long-java.math.RoundingMode-)