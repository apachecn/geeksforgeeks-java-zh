# int math 类

的 Java Guava | sqrt(int x，RoundingMode)方法

> 原文:[https://www . geesforgeks . org/Java-guava-sqrtint-x-rounding mode-method-int math-class/](https://www.geeksforgeeks.org/java-guava-sqrtint-x-roundingmode-mode-method-of-intmath-class/)

番石榴的 IntMath 类的方法 **sqrt(int x，rounding mode)**返回 x 的**平方根**，用指定的舍入模式进行舍入。

**语法:**

```
public static int sqrt(int x, RoundingMode mode)

```

**异常:**

*   **IllegalArgumentException:**if x<0。
*   **算术异常:**如果模式为舍入模式。不必要，sqrt(x)不是整数。

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

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```
// Java code to show implementation of
// sqrt(int x, RoundingMode mode) method
// of Guava's IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int x1 = 226;

        // Using sqrt(int x, RoundingMode mode)
        // method of Guava's IntMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the nearest neighbor unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        int ans1 = IntMath.sqrt(x1,
                                RoundingMode.HALF_EVEN);

        System.out.println("Square root of x1 is: "
                           + ans1);

        int x2 = 154;

        // Using sqrt(int x, RoundingMode mode)
        // method of Guava's IntMath class
        // The RoundingMode FLOOR rounds towards
        // negative infinity.
        int ans2 = IntMath.sqrt(x2,
                                RoundingMode.FLOOR);

        System.out.println("Square root of x2 is: "
                           + ans2);
    }
}
```

**Output:**

```
Square root of x1 is: 15
Square root of x2 is: 12

```

**例 2:**

```
// Java code to show implementation of
// sqrt(int x, RoundingMode mode) method
// of Guava's IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int x1 = -65;
        try {
            // Using sqrt(int x, RoundingMode mode)
            // method of Guava's IntMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the nearest neighbor unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.

            // This should throw "IllegalArgumentException"
            // as x1 < 0
            int ans1 = IntMath.sqrt(x1,
                                    RoundingMode.HALF_EVEN);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
java.lang.IllegalArgumentException: x (-65) must be >= 0

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # sqrt-int-Java . math . round ingmode-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#sqrt-int-java.math.RoundingMode-)