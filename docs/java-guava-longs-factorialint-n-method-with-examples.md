# Java 番石榴| Longs.factorial(int n)方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-阶乘 int-n-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-factorialint-n-method-with-examples/)

番石榴[龙数学类](https://www.geeksforgeeks.org/longmath-class-guava-java/)的**阶乘(int n)** 方法返回前 n 个正整数的乘积，为 n！。

**语法:**

```java
public static long factorial(int n)

```

**参数:**该方法只接受一个参数 **n** ，该参数为整数类型，用于求阶乘。

**返回值:**该方法返回以下值:

*   如果 n 为 0，该方法返回 **1** 。
*   如果结果符合一个长整数，这个方法返回前 n 个正整数的乘积。
*   此方法返回 **Long。最大值**如果结果不符合长。

**异常:**如果 n 为负，方法阶乘(int n)抛出***IllegalArgumentException***。

下面的程序说明了 LongMath.factorial()方法的使用:

**例 1:**

```java
// Java code to show implementation of
// factorial(int n) method of Guava's
// LongMath Class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int n1 = 10;

        // Using factorial(int n) method of
        // Guava's LongMath class
        long ans1 = LongMath.factorial(n1);

        System.out.println("factorial of "
                           + n1 + " is : "
                           + ans1);

        int n2 = 12;

        // Using factorial(int n) method of
        // Guava's LongMath class
        long ans2 = LongMath.factorial(n2);

        System.out.println("factorial of "
                           + n2 + " is : "
                           + ans2);
    }
}
```

**输出:**

```java
factorial of 10 is : 3628800
factorial of 12 is : 479001600

```

**例 2 :**

```java
// Java code to show implementation of
// factorial(int n) method of Guava's
// LongMath Class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static long findFact(int n)
    {
        try {
            // Using factorial(int n) method of
            // Guava's LongMath class
            // This should throw "IllegalArgumentException"
            // as n < 0
            long ans = LongMath.factorial(n);

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
        int n = -5;

        try {

            // Function calling
            findFact(n);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.IllegalArgumentException: n (-5) must be >= 0

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/longmath . html #阶乘-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#factorial-int-)