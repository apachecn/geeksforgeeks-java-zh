# Java 番石榴| Longs.checkedSubtract(长 a，长 b)方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-checked subtractlong-a-long-b-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-checkedsubtractlong-a-long-b-method-with-examples/)

**checkedSubtract(long a，long b)** 是番石榴 [LongMath 类](https://www.geeksforgeeks.org/longmath-class-guava-java/)的一种方法，接受两个参数 **a** 和 **b** ，并返回它们的差值。

**语法:**

```
public static long checkedSubtract(long a, long b)

```

**参数:**该方法接受两个长值 *a* 和 *b* 并计算它们的差值。

**返回值:**该方法返回传递给它的长值之差，前提是不溢出。

**异常:**如果差(即，a–b)在有符号长算术中溢出，方法 checkedSubtract(长 a，长 b)将抛出 ***算术异常*** 。

下面的例子说明了上述方法的实现:

**例 1:**

```
// Java code to show implementation of
// checkedSubtract(long a, long b) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long a1 = 25;
        long b1 = 36;

        // Using checkedSubtract(long a, long b)
        // method of Guava's LongMath class
        long ans1 = LongMath.checkedSubtract(a1, b1);

        System.out.println("Difference of " + a1 + " and "
                           + b1 + " is: " + ans1);

        long a2 = 150;
        long b2 = 667;

        // Using checkedSubtract(long a, long b)
        // method of Guava's LongMath class
        long ans2 = LongMath.checkedSubtract(a2, b2);

        System.out.println("Difference of " + a2 + " and "
                           + b2 + " is: " + ans2);
    }
}
```

**输出:**

```
Difference of 25 and 36 is: -11
Difference of 150 and 667 is: -517

```

**例 2:**

```
// Java code to show implementation of
// checkedSubtract(long a, long b) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static long findDiff(long a, long b)
    {
        try {

            // Using checkedSubtract(long a, long b) method
            // of Guava's LongMath class
            // This should throw "ArithmeticException"
            // as the difference overflows in signed
            // long arithmetic
            long ans = LongMath.checkedSubtract(a, b);

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
        long a = Long.MIN_VALUE;
        long b = 452;

        try {

            // Function calling
            findDiff(a, b);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.lang.ArithmeticException: overflow

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/longmath . html # checked subtract-long-long-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#checkedSubtract-long-long-)