# Java 中的大整数 gcd()方法，带示例

> 原文:[https://www . geesforgeks . org/big integer-gcd-method-in-Java-with-examples/](https://www.geeksforgeeks.org/biginteger-gcd-method-in-java-with-examples/)

[两个数的 GCD(最大公约数)或 HCF(最高公因数)](https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/)是两个数相除的最大数。**T3 大整数。gcd(BigInteger val)** 方法用于计算两个 BigInteger 的 gcd。此方法根据调用此方法的当前大整数和作为参数传递的大整数计算 gcd

**语法:**

```java
public BigInteger gcd(BigInteger val)

```

**参数:**该方法接受参数**值**，该值是要计算 gcd 的两个数字之一。该数字应为 BigInteger 类型。

**返回值:**这个方法返回一个**大整数**，它保存两个大整数的计算 gcd。

下面的程序用来说明 BigInteger 的 gcd()方法。

**例 1:**

```java
// Java program to demonstrate
// gcd() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // BigInteger object to store the result
        BigInteger result;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate gcd
        String input1 = "54";
        String input2 = "42";

        // Creating two BigInteger objects
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Calculate gcd
        result = a.gcd(b);

        // Print result
        System.out.println("The GCD of "
                           + a + " and "
                           + b + " is "
                           + result);
    }
}
```

**输出:**

```java
The GCD of 54 and 42 is 6

```

**例 2:**

```java
// Java program to demonstrate
// gcd() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // BigInteger object to store result
        BigInteger result;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String
        // Holds the values to calculate gcd
        String input1 = "4095484568135646548";
        String input2 = "9014548534231345454";

        // Creating two BigInteger objects
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Calculate gcd
        result = a.gcd(b);

        // Print result
        System.out.println("The GCD of "
                           + a + " and "
                           + b + " is "
                           + result);
    }
}
```

**输出:**

> 4095484568135646548 和 9014548534231345454 的 GCD 为 2

**参考:**[https://docs . Oracle . com/en/Java/javae/12/docs/API/Java . base/Java/math/big integer . html # gcd(Java . math . big integer)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#gcd(java.math.BigInteger))