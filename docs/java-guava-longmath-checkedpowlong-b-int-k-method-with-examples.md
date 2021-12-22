# Java 番石榴| long math . checked Dow(long b，int k)方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-long math-checkedpowlong-b-int-k-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longmath-checkedpowlong-b-int-k-method-with-examples/)

**checkedPow(长 b，长 k)** 是番石榴 **[LongMath Class](https://www.geeksforgeeks.org/longmath-class-guava-java/)** 的一种方法，接受两个参数 **b** 和 **k** ，用来求 b 的 k 次方。

**语法:**

```java
public static long checkedPow(long b, long k)

```

**参数:**该方法接受两个参数，b 和 k，参数 b 称为*基*，加到 k 次幂。

**返回值:**此方法返回 b 的 k 次幂。

**异常:**如果 b 的 k 次方在有符号长算术中溢出，方法 checkedPow(长 b，长 k)抛出 ***算术异常*** 。

以下示例说明了上述方法的实现:

**例 1:**

```java
// Java code to show implementation of
// checkedPow(long b, long k) method of
// Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long b1 = 5;
        int k1 = 7;

        // Using checkedPow(long b, long k) method
        // of Guava's LongMath class
        long ans1 = LongMath.checkedPow(b1, k1);

        System.out.println(b1 + " to the "
                           + k1 + "th power is: "
                           + ans1);

        long b2 = 19;
        int k2 = 4;

        // Using checkedPow(long b, long k) method
        // of Guava's LongMath class
        long ans2 = LongMath.checkedPow(b2, k2);

        System.out.println(b2 + " to the " + k2
                           + "th power is: "
                           + ans2);
    }
}
```

**输出:**

```java
5 to the 7th power is: 78125
19 to the 4th power is: 130321

```

**例 2:**

```java
// Java code to show implementation of
// checkedPow(long b, long k) method of
// Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static long findPow(long b, int k)
    {
        try {

            // Using checkedPow(long b, long k) method of
            // Guava's LongMath class
            // This should raise "ArithmeticException" as
            // b to the kth power overflows in
            // signed long arithmetic
            long ans = LongMath.checkedPow(b, k);

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
        long b = 20;
        int k = 25;

        try {

            // Function calling
            findPow(b, k);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.ArithmeticException: overflow

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/longmath . html # checked Dow-long-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#checkedPow-long-int-)