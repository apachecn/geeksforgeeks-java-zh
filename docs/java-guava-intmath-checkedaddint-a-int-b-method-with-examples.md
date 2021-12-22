# Java 番石榴| IntMath.checkedAdd(int a，int b)方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-int math-checkedaddint-a-int-b-method-with-examples/](https://www.geeksforgeeks.org/java-guava-intmath-checkedaddint-a-int-b-method-with-examples/)

**checkedAdd(int a，int b)** 是番石榴的 [IntMath 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的一种方法，它接受两个参数 **a** 和 **b** ，并返回它们的和。

**语法:**

```java
public static int checkedAdd(int a, int b)

```

**参数:**该方法接受两个整数值 *a* 和 *b* 并计算它们的和。

**返回值:**该方法返回传递给它的 int 值之和，前提是它不溢出。

**异常:**如果和(即，a–b)在有符号整数运算中溢出，方法 CheckEdad(int a，int b)将抛出 ***算法异常*** 。

下面的例子说明了上述方法的实现:

**例 1:**

```java
// Java code to show implementation of
// checkedAdd(int a, int b) method
// of Guava's IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int a1 = 25;
        int b1 = 36;

        // Using checkedAdd(int a, int b)
        // method of Guava's IntMath class
        int ans1 = IntMath.checkedAdd(a1, b1);

        System.out.println("Sum of " + a1 + " and "
                           + b1 + " is: " + ans1);

        int a2 = 150;
        int b2 = 667;

        // Using checkedAdd(int a, int b)
        // method of Guava's IntMath class
        int ans2 = IntMath.checkedAdd(a2, b2);

        System.out.println("Sum of " + a2 + " and "
                           + b2 + " is: " + ans2);
    }
}
```

**Output:**

```java
Sum of 25 and 36 is: 61
Sum of 150 and 667 is: 817

```

**例 2:**

```java
// Java code to show implementation of
// checkedAdd(int a, int b) method
// of Guava's IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findDiff(int a, int b)
    {
        try {

            // Using checkedAdd(int a, int b) method
            // of Guava's IntMath class
            // This should throw "ArithmeticException"
            // as the sum overflows in signed
            // int arithmetic
            int ans = IntMath.checkedAdd(a, b);

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
        int a = Integer.MIN_VALUE;
        int b = 452;

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

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # checkedAdd-int-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#checkedAdd-int-int-)