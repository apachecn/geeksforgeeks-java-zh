# Java 番石榴| IntMath.checkedPow(int b，int k)方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-int math-checkedpowint-b-int-k-method-with-examples/](https://www.geeksforgeeks.org/java-guava-intmath-checkedpowint-b-int-k-method-with-examples/)

**checked Dow(int b，int k)** 是番石榴**的[IntMath Class](https://www.geeksforgeeks.org/intmath-class-guava-java/)T5 的一个方法，接受两个参数 **b** 和 **k** ，用来求 b 的 k 次方。**

**语法:**

```
public static int checkedPow(int b, int k)

```

**参数:**该方法接受两个参数，b 和 k，参数 b 称为*基*，加到 k 次幂。

**返回值:**此方法返回 b 的 k 次幂。

**异常:**如果 b 的 k 次方在有符号整数运算中溢出，方法 checked Dow(int b，int k)抛出 ***算法异常*** 。

以下示例说明了上述方法的实现:

**例 1:**

```
// Java code to show implementation of
// checkedPow(int b, int k) method of
// Guava's IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int b1 = 5;
        int k1 = 7;

        // Using checkedPow(int b, int k) method
        // of Guava's IntMath class
        int ans1 = IntMath.checkedPow(b1, k1);

        System.out.println(b1 + " to the "
                           + k1 + "th power is: "
                           + ans1);

        int b2 = 19;
        int k2 = 4;

        // Using checkedPow(int b, int k) method
        // of Guava's IntMath class
        int ans2 = IntMath.checkedPow(b2, k2);

        System.out.println(b2 + " to the " + k2
                           + "th power is: "
                           + ans2);
    }
}
```

**输出:**

```
5 to the 7th power is: 78125
19 to the 4th power is: 130321

```

**例 2:**

```
// Java code to show implementation of
// checkedPow(int b, int k) method of
// Guava's IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findPow(int b, int k)
    {
        try {

            // Using checkedPow(int b, int k) method of
            // Guava's IntMath class
            // This should raise "ArithmeticException" as
            // b to the kth power overflows in
            // signed int arithmetic
            int ans = IntMath.checkedPow(b, k);

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
        int b = 20;
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

```
java.lang.ArithmeticException: overflow

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # checkedPow-int-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#checkedPow-int-int-)