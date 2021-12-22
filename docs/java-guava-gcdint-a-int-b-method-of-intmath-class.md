# int math 类

的 Java 番石榴| gcd(int a，int b)方法

> 原文:[https://www . geesforgeks . org/Java-guava-gcdint-a-int-b-method-of-int math-class/](https://www.geeksforgeeks.org/java-guava-gcdint-a-int-b-method-of-intmath-class/)

番石榴的 IntMath 类的方法 **gcd(int a，int b)** 返回 a，b 的最大公约数。

**语法:**

```
public static int gcd(int a, int b)

Where a and b are integers.

```

**返回值:**整数 a 和 b 的最大公约数

**异常:**如果 a < 0 或 b < 0，方法 gcd(int a，int b)会抛出***IllegalArgumentException***。

**例 1 :**

```
// Java code to show implementation of
// gcd(int a, int b) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int a1 = 64;
        int b1 = 36;

        // Using gcd(int a, int b) method
        // of Guava's IntMath class
        int ans1 = IntMath.gcd(a1, b1);

        System.out.println("GCD of a1 & b1 is: "
                           + ans1);

        int a2 = 23;
        int b2 = 15;

        // Using gcd(int a, int b) method
        // of Guava's IntMath class
        int ans2 = IntMath.gcd(a2, b2);

        System.out.println("GCD of a2 & b2 is: "
                           + ans2);
    }
}
```

**输出:**

```
GCD of a1 & b1 is: 4
GCD of a2 & b2 is: 1

```

**例 2 :**

```
// Java code to show implementation of
// gcd(int a, int b) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int a1 = -5;
        int b1 = 15;

        try {
            // Using gcd(int a, int b) method
            // of Guava's IntMath class
            // This should throw "IllegalArgumentException"
            // as a1 < 0
            int ans1 = IntMath.gcd(a1, b1);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.lang.IllegalArgumentException: a (-5) must be >= 0

```

**注意:**如果 a = = 0&b = = 0，则方法返回 0。

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # gcd-int-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#gcd-int-int-)