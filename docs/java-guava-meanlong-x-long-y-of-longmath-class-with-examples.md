# Java 番石榴| long math 类的均值(长 x，长 y)带示例

> 原文:[https://www . geesforgeks . org/Java-guava-mean long-x-long-y-of-long math-class-with-examples/](https://www.geeksforgeeks.org/java-guava-meanlong-x-long-y-of-longmath-class-with-examples/)

番石榴[长数学类](https://www.geeksforgeeks.org/longmath-class-guava-java/)的**均值(长 x，长 y)** 方法接受两个参数 x 和 y，并计算它们的算术平均值，四舍五入到负无穷大。这种方法具有溢出弹性。

**语法:**

```
public static long mean(long x, long y)

```

**参数:**该方法接受长类型的两个参数 x 和 y。

**返回值:**该方法返回 x 和 y 的算术平均值，向负无穷大舍入。

**异常:**方法没有任何异常。

**例 1:**

```
// Java code to show implementation of
// mean(long x, long y) method of Guava's
// LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long x = 1542;
        long y = 421;

        // Using mean(long x, long y)
        // method of Guava's LongMath class
        long ans = LongMath.mean(x, y);

        // Displaying the result
        System.out.println("Mean of " + x + " and "
                           + y + " is : " + ans);
    }
}
```

**输出:**

```
Mean of 1542 and 421 is : 981

```

**例 2:**

```
// Java code to show implementation of
// mean(long x, long y) method of Guava's
// LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long x = 65;
        long y = 41;

        // Using mean(long x, long y)
        // method of Guava's LongMath class
        long ans = LongMath.mean(x, y);

        // Displaying the result
        System.out.println("Mean of " + x + " and "
                           + y + " is : " + ans);
    }
}
```

**输出:**

```
Mean of 65 and 41 is : 53

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/longmath . html # mean-long-long-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#mean-long-long-)