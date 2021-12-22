# Java 番石榴| int math 类的二项式()方法

> 原文:[https://www . geesforgeks . org/Java-guava-二项式-of-intmath-class/](https://www.geeksforgeeks.org/java-guava-binomial-method-of-intmath-class/)

[番石榴的 IntMath 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的**二项式(int n，int k)** 方法接受两个参数 **n** 和 **k** ，计算二项式系数![{n}\choose{k}](img/2c819c9fb992984b4189ea89af024f10.png "Rendered by QuickLaTeX.com")的值。

如果计算值溢出整数的最大值，则该方法返回整数。MAX_VALUE 或者换句话说，一个整数的最大值。

**语法:**

```java
public static int binomial(int n, int k)

```

**参数**:该方法接受两个参数 **n** 和 **k** ，计算二项式系数![{n}\choose{k}](img/2c819c9fb992984b4189ea89af024f10.png "Rendered by QuickLaTeX.com")的值。

**返回值:**该方法返回 n 和 k 的二项式系数。

**异常:**法二项式(int n，int k)抛出***IllegalArgumentException***if n**<**0，k **<** 0 或 k **>** n。

以下示例说明了 IntMath 类的二项式()方法:

**例 1 :**

```java
// Java code to show implementation of
// binomial(int n, int k) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int n = 5;
        int k = 2;

        // Using binomial(int n, int k) method of
        // Guava's IntMath class
        int ans = IntMath.binomial(n, k);

        System.out.println("Binomial Coefficient of " + n 
                              + " and " + k + " is : " + ans);

        int n1 = 15;
        int k1 = 9;

        // Using binomial(int n, int k) method of
        // Guava's IntMath class
        int ans1 = IntMath.binomial(n1, k1);

        System.out.println("Binomial Coefficient of " + n1 
                             + " and " + k1 + " is : " + ans1);
    }
}
```

**Output:**

```java
Binomial Coefficient of 5 and 2 is : 10
Binomial Coefficient of 15 and 9 is : 5005

```

**例 2 :**

```java
// Java code to show implementation of
// binomial(int n, int k) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findBinomial(int n, int k)
    {

        try {
            // Using binomial(int n, int k)
            // method of Guava's IntMath class
            // This should throw "IllegalArgumentException"
            // as k < 0
            int ans = IntMath.binomial(n, k);

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
        int n = 5;
        int k = 7;

        try {

            // Function calling
            findBinomial(n, k);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.lang.IllegalArgumentException: k (7) > n (5)

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # binomial-int-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#binomial-int-int-)