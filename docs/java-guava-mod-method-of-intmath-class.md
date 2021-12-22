# int math 类的 Java 番石榴| mod()方法

> 原文:[https://www . geesforgeks . org/Java-guava-mod-of-in math-class/](https://www.geeksforgeeks.org/java-guava-mod-method-of-intmath-class/)

[番石榴的 IntMath 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的 **mod(int x，int m)** 方法接受两个参数 **x** 和 **m** ，用于计算 m 下 **x 模数的值。**

**语法:**

```java
public static int mod(int x, int m)

```

**参数**:该方法接受两个整数类型的参数 **x** 和 **m** ，计算 **x 模 m** 。

**返回值:**该方法返回 x mod m，它将是一个小于 m 的非负值

**异常:**如果 m < = 0，方法 mod(int x，int m)抛出 ***算法异常*** 。

下面的例子说明了 mod(int x，int m)方法:

**例 1 :**

```java
// Java code to show implementation of
// mod(int x, int m) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int x1 = -84;
        int m1 = 5;

        int ans1 = IntMath.mod(x1, m1);

        // Using mod(int x, int m)
        // method of Guava's IntMath class
        System.out.println(x1 + " mod " + m1 + " is : " + ans1);

        int x2 = 14;
        int m2 = 6;

        int ans2 = IntMath.mod(x2, m2);

        // Using mod(int x, int m)
        // method of Guava's IntMath class
        System.out.println(x2 + " mod " + m2 + " is : " + ans2);
    }
}
```

输出:

```java
-84 mod 5 is : 1
14 mod 6 is : 2

```

**例 2 :**

```java
// Java code to show implementation of
// mod(int x, int m) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findMod(int x, int m)
    {
        try {
            // Using mod(int x, int m)
            // method of Guava's IntMath class
            // This should throw "ArithmeticException"
            // as m <= 0
            int ans = IntMath.mod(x, m);

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
        int x = 14;
        int m = -3;

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

输出:

```java
java.lang.ArithmeticException: Modulus -3 must be > 0

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # mod-int-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#mod-int-int-)