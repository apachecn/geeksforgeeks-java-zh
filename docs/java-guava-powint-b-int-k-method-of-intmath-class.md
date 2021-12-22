# int math 类

的 Java 番石榴| pow(int b，int k)方法

> 原文:[https://www . geesforgeks . org/Java-guava-pow int-b-int-k-method-of-int math-class/](https://www.geeksforgeeks.org/java-guava-powint-b-int-k-method-of-intmath-class/)

番石榴的 IntMath 类的方法**幂(int b，int k)** 将 **b 返回到第 k 次幂**。即使结果溢出，也等于 BigInteger.valueOf(b)。功率(k)。intValue()。该实现在 **O(log k)** 时间运行。

**语法:**

```
public static int pow(int b, int k)

```

**异常:**法幂(int b，int k)抛出*T3】IllegalArgumentExceptionT5】如果 k < 0。*

**例 1:**

```
// Java code to show implementation of
// pow(int b, int k) method of Guava's
// IntMath class

import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findPow(int b, int k)
    {

        // Using pow(int b, int k)
        // method of Guava's IntMath class
        int ans = IntMath.pow(b, k);

        // Return the answer
        return ans;
    }

    // Driver code
    public static void main(String args[])
    {
        int b = 4;
        int k = 5;

        int ans = findPow(b, k);

        System.out.println(b + " to the " + k
                           + "th power is: "
                           + ans);

        b = 12;
        k = 3;

        ans = findPow(b, k);

        System.out.println(b + " to the " + k
                           + "th power is: "
                           + ans);
    }
}
```

**Output:**

```
4 to the 5th power is: 1024
12 to the 3th power is: 1728

```

**例 2 :**

```
// Java code to show implementation of
// pow(int b, int k) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findPow(int b, int k)
    {

        try {
            // Using pow(int b, int k)
            // method of Guava's IntMath class
            // This should throw "IllegalArgumentException"
            // as k < 0
            int ans = IntMath.pow(b, k);

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
        int b = 4;
        int k = -5;

        try {
            // Using pow(int b, int k)
            // method of Guava's IntMath class
            // This should throw "IllegalArgumentException"
            // as k < 0
            IntMath.pow(b, k);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.lang.IllegalArgumentException: exponent (-5) must be >= 0

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # pow-int-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#pow-int-int-)