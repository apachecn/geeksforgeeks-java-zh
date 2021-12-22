# Java 番石榴| int math 的 log2(int x，RoundingMode)方法

> 原文:[https://www . geesforgeks . org/Java-guava-log2 int-x-rounding mode-method-of-int math/](https://www.geeksforgeeks.org/java-guava-log2int-x-roundingmode-mode-method-of-intmath/)

[番石榴的 IntMath](https://www.geeksforgeeks.org/intmath-class-guava-java/) 的 **log2(int x，rounding mode)**方法接受两个参数，根据第二个参数指定的舍入方式计算第一个参数舍入后的基数-2 对数值。

**语法:**

```
public static int log2(int x, RoundingMode mode)

```

**参数:**该方法取 2 个参数，其中 ***x*** 为整数， ***模式*** 为指定取整模式。

**返回值:**该方法返回 x 的以 2 为底的对数，根据指定的舍入方式进行舍入。

**异常:**

*   **IllegalArgumentException:**if x<= 0。
*   **算术异常:**如果模式为舍入模式。不必要，x 不是 2 的幂。

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

下面的例子说明了番石榴整数 log2()方法的实现:

**例 1 :**

```
// Java code to show implementation of
// log2(int x, RoundingMode mode) method
// of Guava's IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int a1 = 1542;

        // Using log2(int x, RoundingMode mode)
        // method of Guava's IntMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the "nearest neighbor" unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        System.out.println(IntMath.log2(a1, RoundingMode.HALF_EVEN));

        int a2 = 451;

        // Using log2(int x, RoundingMode mode)
        // method of Guava's IntMath class
        // The RoundingMode HALF_DOWN rounds towards
        // "nearest neighbor" unless both neighbors
        // are equidistant, in which case round down.
        System.out.println(IntMath.log2(a2, RoundingMode.HALF_DOWN));
    }
}
```

**Output:**

```
11
9

```

**例 2 :**

```
// Java code to show implementation of
// log2(int x, RoundingMode mode) method
// of Guava's IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findlog2(int x, RoundingMode mode)
    {
        try {
            // Using log2(int x, RoundingMode mode)
            // method of Guava's IntMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the "nearest neighbor" unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.
            // This should throw "IllegalArgumentException"
            // as x <= 0
            int ans = IntMath.log2(x, mode);

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
        int x = -152;

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

**Output:**

```
java.lang.IllegalArgumentException: x (-152) must be > 0

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # log2-int-Java . math . round ingmode-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#log2-int-java.math.RoundingMode-)