# bigintermath ceilingPowerOfTwo()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/bigintermath-ceilingpoweroftwo-function-guava-Java/](https://www.geeksforgeeks.org/bigintegermath-ceilingpoweroftwo-function-guava-java/)

[番石榴的大整数类](https://www.geeksforgeeks.org/bigintegermath-class-guava-java/)的**ceilingPowerOfTwo(big integer x)**方法返回大于或等于 x 的 2 的 ***最小幂*** ，这相当于 BigInteger.valueOf(2)。功率(log2(x，天花板))。

**语法:**

```
public static BigInteger 
    ceilingPowerOfTwo(BigInteger x)

```

**参数:**该方法以数字 **x** 为参数，求其 2 的上幂。

**返回值:**此方法返回给定数 x 的 2 的上限幂。

**异常:**如果 x < = 0，此方法抛出***IllegalArgumentException***。

以下示例说明了 BigIntegerMath . CeilingPoweroftwo()方法:

**例 1:**

```
// Java code to show implementation of
// ceilingPowerOfTwo(BigInteger x) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        BigInteger n1 = BigInteger.valueOf(25);

        // Using ceilingPowerOfTwo(BigInteger x) method of
        // Guava's BigIntegerMath class
        BigInteger ans = BigIntegerMath.ceilingPowerOfTwo(n1);

        System.out.println("Smallest power of 2 greater "
                           + "than or equal to "
                           + n1 + " is: " + ans);

        BigInteger n2 = BigInteger.valueOf(65);

        // Using ceilingPowerOfTwo(BigInteger x) method of
        // Guava's BigIntegerMath class
        BigInteger ans1 = BigIntegerMath.ceilingPowerOfTwo(n2);

        System.out.println("Smallest power of 2 greater "
                           + "than or equal to "
                           + n2 + " is: " + ans1);
    }
}
```

**输出:**

```
Smallest power of 2 greater than or equal to 25 is: 32
Smallest power of 2 greater than or equal to 65 is: 128

```

**例 2:**

```
// Java code to show implementation of
// ceilingPowerOfTwo(BigInteger x) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {

        try {

            BigInteger n = BigInteger.valueOf(0);

            // Using ceilingPowerOfTwo(BigInteger x) method of
            // Guava's BigIntegerMath class
            // This should raise "IllegalArgumentException"
            // as n is <= 0
            BigInteger ans = BigIntegerMath.ceilingPowerOfTwo(n);

            System.out.println("Smallest power of 2 greater "
                               + "than or equal to n is : " + ans);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Exception: java.lang.IllegalArgumentException: x (0) must be > 0

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/math/bigintermath . html # ceilingPowerOfTwo-Java . math . biginger-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#ceilingPowerOfTwo-java.math.BigInteger-)