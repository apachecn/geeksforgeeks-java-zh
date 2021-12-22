# bigentermath floweroftwo()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/bigintermath-floweroftwo-function-guava-Java/](https://www.geeksforgeeks.org/bigintegermath-floorpoweroftwo-function-guava-java/)

[番石榴的大整数类](https://www.geeksforgeeks.org/bigintegermath-class-guava-java/)的方法**flower powerof two(大整数 x)** 返回小于或等于 x 的 2 的最大幂，这相当于大整数. valueOf(2)。pow(log2(x，FLOOR))。
**语法:**

```java
public static BigInteger floorPowerOfTwo(BigInteger x)
```

**参数:**该方法以大整数 **x** 为参数，求其二的底幂。
**返回值:**此方法返回小于等于 x 的 2 的最大幂。
**异常:**此方法抛出***IllegalArgumentException***如果 **x < = 0** 。
以下示例说明了 BigIntegerMath.floorPowerOfTwo()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show implementation of
// floorPowerOfTwo() method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        BigInteger n1 = BigInteger.valueOf(10);

        // Using floorPowerOfTwo(BigInteger x) method
        // of Guava's BigIntegerMath class
        BigInteger
            ans1
            = BigIntegerMath.floorPowerOfTwo(n1);

        System.out.println("Largest power of 2 less "
                           + "than or equal to " + n1
                           + " is: " + ans1);

        BigInteger n2 = BigInteger.valueOf(127);

        // Using floorPowerOfTwo(BigInteger x) method
        // of Guava's BigIntegerMath class
        BigInteger
            ans2
            = BigIntegerMath.floorPowerOfTwo(n2);

        System.out.println("Largest power of 2 less "
                           + "than or equal to " + n2
                           + " is: " + ans2);
    }
}
```

**输出:**

```java
Largest power of 2 less than or equal to 10 is: 8
Largest power of 2 less than or equal to 127 is: 64
```

**示例 2:** 显示非法文档异常

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show implementation of
// floorPowerOfTwo(BigInteger x) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {

        try {
            BigInteger n1 = BigInteger.valueOf(-3);

            // Using floorPowerOfTwo(BigInteger x) method
            // of Guava's BigIntegerMath class
            // This should raise "IllegalArgumentException"
            // as x <= 0
            BigInteger
                ans1
                = BigIntegerMath.floorPowerOfTwo(n1);

            System.out.println("Largest power of 2 less "
                               + "than or equal to " + n1
                               + " is: " + ans1);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.IllegalArgumentException: x (-3) must be > 0
```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/math/bigintermath . html # floweroftwo-Java . math . biginger-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#floorPowerOfTwo-java.math.BigInteger-)