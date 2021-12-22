# 用欧几里德算法求两个数的 GCD 和 LCM 的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序查找-gcd-和-LCM-两个数字-使用-euclids-算法/](https://www.geeksforgeeks.org/java-program-to-find-gcd-and-lcm-of-two-numbers-using-euclids-algorithm/)

**GCD** 或两个给定数 A 和 B 的最大公约数是将 A 和 B 完全除的最高数，即每种情况下余数均为 0。 **LCM** 或两个给定数 A 和 B 的最小公倍数是能被 A 和 B 除的最小数，在每种情况下余数都为 0。

两个数的 LCM 可以用欧几里德的方法用 A 和 b 的 GCD 来计算

> **LCM(A，B) = (a * b) / GCD(A，B)**

**示例:**

> **输入:** A = 20，B = 30
> 
> **输出:**
> GCD = 10
> LCM = 60
> 
> **说明:**
> 20 和 30 除的最高数是 10。所以 20，30 的 GCD 是 10。
> 能被 20 和 30 除，剩下余数 0 的最小数是 60。
> 所以 20 和 30 的 LCM 是 60。
> 
> **输入:** A= 33，B= 40
> 
> **输出:**
> GCD = 1
> LCM = 1320

### 欧几里德算法计算几何中心距离；

这种计算 gcd 的方法是基于这样的原理，即两个数字 A 和 B 的 GCD 保持不变，即使用 A 和 B 的模代替较大的数字。在这种方法中，我们通过用 A 和 B 的模代替 B and B 来重复对 A 和 B 执行 GCD 操作，直到模变成 0。

下面是使用欧几里德算法求两个数的广义循环数和广义循环数的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to compute
// GCD of two numbers
// using Euclid's algorithm

import java.io.*;

class GFG {

    // gcd method returns the GCD of a and b
    static int gcd(int a, int b) {

        // if b=0, a is the GCD
        if (b == 0)
            return a;

        // call the gcd() method recursively by
        // replacing a with b and b with
        // modulus(a,b) as long as b != 0
        else
            return gcd(b, a % b);
    }

    // lcm() method returns the LCM of a and b
    static int lcm(int a, int b, int gcdValue)
    {
        return Math.abs(a * b) / gcdValue;
    }

    // Driver method
    public static void main(String[] args) {

        int a = 20, b = 30, gcdValue;
        gcdValue = gcd(a, b);

        // calling gcd() over
        System.out.println("GCD = " + gcdValue);

        // calling lcm() over integers 30 and 20
        System.out.println("LCM = " + lcm(a, b, gcdValue));
    }
}
```

**Output**

```java
GCD = 10
LCM = 60
```