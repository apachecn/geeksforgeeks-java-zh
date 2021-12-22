# Java 番石榴| LongMath.checkedMultiply(int a，int b)方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-long math-checked multiplient-a-int-b-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longmath-checkedmultiplyint-a-int-b-method-with-examples/)

**检查倍数(长 a，长 b)** 是番石榴[长数学类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的一种方法，它接受两个参数 **a** 和 **b** ，并返回它们的产品。

**语法:**

```java
public static long checkedMultiply(long a, long b)

```

**参数:**该方法接受两个长值 *a* 和 *b* 并计算它们的乘积。

**返回值:**方法返回传递给它的长值的乘积，前提是不溢出。

**异常:**如果乘积(即，a–b)在有符号长算术中溢出，则方法 checkedMultiply(长 a，长 b)会抛出 ***算术异常*** 。

下面的例子说明了上述方法的实现:

**例 1:**

```java
// Java code to show implementation of
// checkedMultiply(long a, long b) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long a1 = 25;
        long b1 = 36;

        // Using checkedMultiply(long a, long b)
        // method of Guava's LongMath class
        long ans1 = LongMath.checkedMultiply(a1, b1);

        System.out.println("Product of " + a1 + " and "
                           + b1 + " is: " + ans1);

        long a2 = 150;
        long b2 = 667;

        // Using checkedMultiply(long a, long b)
        // method of Guava's LongMath class
        long ans2 = LongMath.checkedMultiply(a2, b2);

        System.out.println("Product of " + a2 + " and "
                           + b2 + " is: " + ans2);
    }
}
```

**Output:**

```java
Product of 25 and 36 is: 900
Product of 150 and 667 is: 100050

```

**例 2:**

```java
// Java code to show implementation of
// checkedMultiply(long a, long b) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static long findDiff(long a, long b)
    {
        try {

            // Using checkedMultiply(long a, long b) method
            // of Guava's LongMath class
            // This should throw "ArithmeticException"
            // as the product overflows in signed
            // long arithmetic
            long ans = LongMath.checkedMultiply(a, b);

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

**Output:**

```java
java.lang.ArithmeticException: overflow

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/longmath . html # checked multiply-long-long-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#checkedMultiply-long-long-)