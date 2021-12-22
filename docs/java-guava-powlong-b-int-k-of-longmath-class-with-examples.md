# Java 番石榴| long math 类的 pow(long b，int k)带示例

> 原文:[https://www . geesforgeks . org/Java-guava-pow long-b-int-k-of-long math-class-with-examples/](https://www.geeksforgeeks.org/java-guava-powlong-b-int-k-of-longmath-class-with-examples/)

番石榴[龙数学类](https://www.geeksforgeeks.org/longmath-class-guava-java/)的方法**幂(长 b，int k)** 将 **b 返回到第 kth 幂**。即使结果溢出，也等于 BigInteger.valueOf(b)。功率(k)。longValue()。该实现在 **O(log k)** 时间运行。

**语法:**

```java
public static long pow(long b, int k)

```

**参数:**该方法接受两个参数，b 和 k，参数 b 称为*基*，加到 k 次幂。

**返回值:**此方法返回 b 的 k 次幂。

**异常:**如果 k 为负，此方法抛出***IllegalArgumentException***。

**例 1:**

```java
// Java code to show implementation of
// pow(long b, int k) method of Guava's
// LongMath Class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long b1 = 4;
        int k1 = 5;

        long ans1 = LongMath.pow(b1, k1);

        System.out.println(b1 + " to the " + k1
                           + "th power is: "
                           + ans1);

        long b2 = 12;
        int k2 = 3;

        long ans2 = LongMath.pow(b2, k2);

        System.out.println(b2 + " to the " + k2
                           + "rd power is: "
                           + ans2);
    }
}
```

**输出:**

```java
4 to the 5th power is: 1024
12 to the 3rd power is: 1728

```

**例 2:**

```java
// Java code to show implementation of
// pow(long b, int k) method of Guava's
// LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static long findPow(long b, int k)
    {
        try {
            // Using pow(long b, int k)
            // method of Guava's LongMath class
            // This should throw "IllegalArgumentException"
            // as k < 0
            long ans = LongMath.pow(b, k);

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
        long b = 4;
        int k = -5;

        try {
            // Using pow(long b, int k)
            // method of Guava's LongMath class
            // This should throw "IllegalArgumentException"
            // as k < 0
            LongMath.pow(b, k);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.IllegalArgumentException: exponent (-5) must be >= 0

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/longmath . html # pow-long-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#pow-long-int-)