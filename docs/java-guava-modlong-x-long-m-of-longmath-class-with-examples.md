# long math 类的 Java 番石榴| mod(长 x，长 m)带示例

> 原文:[https://www . geesforgeks . org/Java-guava-modlong-x-long-m-of-long math-class-with-examples/](https://www.geeksforgeeks.org/java-guava-modlong-x-long-m-of-longmath-class-with-examples/)

番石榴[龙数学类](https://www.geeksforgeeks.org/longmath-class-guava-java/)的 **mod(长 x，长 m)** 方法接受两个参数 x 和 m，用于计算 m 下 **x 模数的值。**

**语法:**

```java
public static long mod(long x, long m)

```

**参数:**该方法接受长型的两个参数 x 和 m 来计算 x 模 m。

**返回值:**该方法返回 x mod m，它将是一个小于 m 的非负值

**异常:**方法 mod(长 x，长 m)如果 m < = 0 则抛出 ***算法异常*** 。

以下示例说明了 mod(长 x，长 m)方法:

**例 1 :**

```java
// Java code to show implementation of
// mod(long x, long m) method of Guava's
// LongMath class
import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long x1 = -77;
        long m1 = 4;

        long ans1 = LongMath.mod(x1, m1);

        // Using mod(long x, long m)
        // method of Guava's LongMath class
        System.out.println(x1 + " mod "
                           + m1 + " is : " + ans1);

        long x2 = 22;
        long m2 = 6;

        long ans2 = LongMath.mod(x2, m2);

        // Using mod(long x, long m)
        // method of Guava's LongMath class
        System.out.println(x2 + " mod "
                           + m2 + " is : " + ans2);
    }
}
```

**输出:**

```java
-77 mod 4 is : 3
22 mod 6 is : 4

```

**例 2:**

```java
// Java code to show implementation of
// mod(long x, long m) method of Guava's
// LongMath class
import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static long findMod(long x, long m)
    {
        try {
            // Using mod(long x, long m)
            // method of Guava's LongMath class
            // This should throw "ArithmeticException"
            // as m <= 0
            long ans = LongMath.mod(x, m);

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
        long x = 11;
        long m = -5;

        try {
            // Function calling
            findMod(x, m);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.ArithmeticException: Modulus must be positive

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/longmath . html # mod-long-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#mod-long-int-)