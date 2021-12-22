# 计算 GCD 的 Java 程序

> 原文:[https://www.geeksforgeeks.org/java-program-to-compute-gcd/](https://www.geeksforgeeks.org/java-program-to-compute-gcd/)

[两个给定数 **A** 和 **B** 的 GCD](https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/) (最大公约数)是能完全除 A 和 B 的最高数，即每种情况下余数均为 0。GCD 也被称为 HCF(最高公因数)。有各种方法可以找到两个给定数字的 GCD。

**接近:**

给定的两个数字 A 和 B 的 GCD 可以用不同的方法计算。

1.  Universal method
2.  Euclidean algorithm (by repeated subtraction)
3.  Euclidean algorithm (by repeating division)

**示例:**

```java
Input: 20, 30
Output: GCD(20, 30) =10
Explanation: 10 is the highest integer which divides both 20 and 30 leaving 0 remainder

Input: 36, 37
Output: GCD(36, 37) = 1
Explanation: 36 and 37 don't have any factors in common except 1\. So, 1 is the gcd of 36 and 37
```

**注:**如果 A、B 是[同素](https://www.geeksforgeeks.org/check-two-numbers-co-prime-not/)，则 gcd(A、B) = 1。

**一般方法:**

在计算 GCD 的一般方法中，我们实际上实现了 GCD 的定义。

*   First, find out all the factors of A and B respectively.
*   Then list the common factors of A and B.
*   The highest of these common factors is GCD of A and B.

**例:**

```java
A = 20, B = 30
Factors of A : (1, 2, 4, 5, 10, 20)
Factors of B : (1, 2, 3, 5, 6, 10, 15, 30)
Common factors of A and B : (1, 2, 5, 10)
Highest of the Common factors (GCD) = 10
```

很明显，20 和 30 的 GCD 不能大于 20。所以我们必须检查 1 到 20 之间的数字。此外，我们需要最大的约数。因此，从后向迭代以减少计算时间。

## 爪哇

```java
// Java program to compute GCD of
// two numbers using general
// approach
import java.io.*;

class GFG {

    // gcd() method, returns the GCD of a and b
    static int gcd(int a, int b)
    {
        // stores minimum(a, b)
        int i;
        if (a < b)
            i = a;
        else
            i = b;

        // take a loop iterating through smaller number to 1
        for (i = i; i > 1; i--) {

            // check if the current value of i divides both
            // numbers with remainder 0 if yes, then i is
            // the GCD of a and b
            if (a % i == 0 && b % i == 0)
                return i;
        }

        // if there are no common factors for a and b other
        // than 1, then GCD of a and b is 1
        return 1;
    }
    // Driver method
    public static void main(String[] args)
    {
        int a = 30, b = 20;

        // calling gcd() method over
        // the integers 30 and 20
        System.out.println("GCD = " + gcd(b, a));
    }
}
```

**输出**

```java
GCD = 10
```

**欧几里德算法(重复减法):**

这种方法的原理是，即使我们用 A 和 B 之间的差替换较大的数字，两个数字 A 和 B 的 GCD 也将相同。在这种方法中，只要差大于 0，我们就通过用差(A，B)替换 B and B 来重复对 A 和 B 执行 GCD 操作。

**示例**

```java
A = 30, B = 20
gcd(30, 20) -> gcd(A, B)
gcd(20, 30 - 20) = gcd(20,10) -> gcd(B,B-A)
gcd(30 - 20, 20 - (30 - 20)) = gcd(10, 10) -> gcd(B - A, B - (B - A))
gcd(10, 10 - 10) = gcd(10, 0)
here, the difference is 0
So stop the procedure. And 10 is the GCD of 30 and 20
```

## Java

```java
// Java program to compute GCD
// of two numbers using Euclid's
// repeated subtraction approach
import java.io.*;

class GFG {

    // gcd method returns the GCD of a and b
    static int gcd(int a, int b)
    {
        // if b=0, a is the GCD
        if (b == 0)
            return a;

        // call the gcd() method recursively by
        // replacing a with b and b with
        // difference(a,b) as long as b != 0
        else
            return gcd(b, Math.abs(a - b));
    }

    // Driver method
    public static void main(String[] args)
    {
        int a = 30, b = 20;

        // calling gcd() over
        // integers 30 and 20
        System.out.println("GCD = " + gcd(a, b));
    }
}
```

**输出**

```java
GCD = 10
```

**欧几里德算法(重复除法):**

这种方法类似于重复减法。但是，在这种方法中，我们用 A 和 B 的模量代替 B，而不是差值。

**示例:**

```java
A = 30, B = 20
gcd(30, 20) -> gcd(A, B)
gcd(20, 30 % 20) = gcd(20, 10) -> gcd(B, A % B)
gcd(10, 20 % 10) = gcd(10, 10) -> gcd(A % B, B % (A % B))
gcd(10, 10 % 10) = gcd(10, 0)
here, the modulus became 0
So, stop the procedure. And 10 is the GCD of 30 and 20
```

## Java

```java
// Java program to compute GCD
// of two numbers using Euclid's
// repeated division approach
import java.io.*;
import java.util.*;

class GFG {

    // gcd method returns the GCD of a and b
    static int gcd(int a, int b)
    {
        // if b=0, a is the GCD
        if (b == 0)
            return a;

        // call the gcd() method recursively by
        // replacing a with b and b with
        // modulus(a,b) as long as b != 0
        else
            return gcd(b, a % b);
    }
    // Driver method
    public static void main(String[] args)
    {
        int a = 20, b = 30;

        // calling gcd() over
        // integers 30 and 20
        System.out.println("GCD = " + gcd(a, b));
    }
}
```

**输出**

```java
GCD = 10
```

欧几里德的重复除法是所有方法中最常用的。