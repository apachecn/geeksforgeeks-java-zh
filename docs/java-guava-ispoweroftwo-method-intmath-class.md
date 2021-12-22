# Java 番石榴| isPowerOfTwo()方法 IntMath Class

> 原文:[https://www . geesforgeks . org/Java-guava-ispoweroftwo-method-int math-class/](https://www.geeksforgeeks.org/java-guava-ispoweroftwo-method-intmath-class/)

[番石榴的 IntMath 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的**是 PowerOfTwo()** 方法，用于检查一个数是否是二的幂。它接受要检查的数字作为参数，并根据该数字是否为 2 的幂返回布尔值 true 或 false。

**语法:**

```
public static boolean isPowerOfTwo(int x)

```

**参数**:该方法接受一个整数类型的单参数 **x** 。

**返回值:**如果 x 代表 2 的幂，则该方法返回 ***真*** ，如果 x 不代表 2 的幂，则返回 ***假*** 。

**异常:**方法没有任何异常。

**注意:**这与 Integer.bitCount(x) == 1 不同，因为 Integer.bitCount(Integer。最小值)= 1，但为整数。最小值不是 2 的幂。

**例 1 :**

```
// Java code to show implementation of
// isPowerOfTwo(int x) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int a1 = 63;

        // Using isPowerOfTwo(int x) method
        // of Guava's IntMath class
        if (IntMath.isPowerOfTwo(a1))
            System.out.println(a1 + " is power of 2");
        else
            System.out.println(a1 + " is not power of 2");

        int a2 = 1024;

        // Using isPowerOfTwo(int x) method
        // of Guava's IntMath class
        if (IntMath.isPowerOfTwo(a2))
            System.out.println(a2 + " is power of 2");
        else
            System.out.println(a2 + " is not power of 2");
    }
}
```

输出:

```
63 is not power of 2
1024 is power of 2

```

**例 2 :**

```
// Java code to show implementation of
// isPowerOfTwo(int x) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int a1 = 10;

        // Using isPowerOfTwo(int x) method
        // of Guava's IntMath class
        if (IntMath.isPowerOfTwo(a1))
            System.out.println(a1 + " is power of 2");
        else
            System.out.println(a1 + " is not power of 2");

        int a2 = 256;

        // Using isPowerOfTwo(int x) method
        // of Guava's IntMath class
        if (IntMath.isPowerOfTwo(a2))
            System.out.println(a2 + " is power of 2");
        else
            System.out.println(a2 + " is not power of 2");
    }
}
```

输出:

```
10 is not power of 2
256 is power of 2

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # isPowerOfTwo-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#isPowerOfTwo-int-)