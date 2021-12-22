# Java 番石榴| IntMath.checkedMultiply(int a，int b)方法，带示例

> 原文:[https://www . geeksforgeeks . org/Java-guava-int math-checked multiplient-a-int-b-method-with-examples/](https://www.geeksforgeeks.org/java-guava-intmath-checkedmultiplyint-a-int-b-method-with-examples/)

**checkedMultiply(int a，int b)** 是番石榴 [IntMath 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的一种方法，接受两个参数 **a** 和 **b** ，并返回它们的产品。

**语法:**

```
public static int checkedMultiply(int a, int b)

```

**参数:**该方法接受两个整数值 *a* 和 *b* 并计算它们的乘积。

**返回值:**方法返回传递给它的 int 值的乘积，前提是它不溢出。

**异常:**如果乘积(即 a–b)在有符号整数运算中溢出，方法 checkedMultiply(int a，int b)将抛出 ***算术异常*** 。

下面的例子说明了上述方法的实现:

**例 1:**

```
// Java code to show implementation of
// checkedMultiply(int a, int b) method
// of Guava's IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int a1 = 25;
        int b1 = 36;

        // Using checkedMultiply(int a, int b)
        // method of Guava's IntMath class
        int ans1 = IntMath.checkedMultiply(a1, b1);

        System.out.println("Product of " + a1 + " and "
                           + b1 + " is: " + ans1);

        int a2 = 150;
        int b2 = 667;

        // Using checkedMultiply(int a, int b)
        // method of Guava's IntMath class
        int ans2 = IntMath.checkedMultiply(a2, b2);

        System.out.println("Product of " + a2 + " and "
                           + b2 + " is: " + ans2);
    }
}
```

**输出:**

```
Product of 25 and 36 is: 900
Product of 150 and 667 is: 100050

```

**例 2:**

```
// Java code to show implementation of
// checkedMultiply(int a, int b) method
// of Guava's IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findDiff(int a, int b)
    {
        try {

            // Using checkedMultiply(int a, int b) method
            // of Guava's IntMath class
            // This should throw "ArithmeticException"
            // as the product overflows in signed
            // int arithmetic
            int ans = IntMath.checkedMultiply(a, b);

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

**输出:**

```
java.lang.ArithmeticException: overflow

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # checkedMultiply-int-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#checkedMultiply-int-int-)