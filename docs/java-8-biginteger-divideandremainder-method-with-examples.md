# Java 8 | BigInteger divideandreminder()方法带示例

> 原文:[https://www . geesforgeks . org/Java-8-big integer-divideandreminder-method-with-examples/](https://www.geeksforgeeks.org/java-8-biginteger-divideandremainder-method-with-examples/)

**Java 8 中引入了 Java . math . big integer . divideandreminder(big integer val)**。在调用此方法的 BigInteger 和作为参数传递给另一个方法的 BigInteger 之间应用除法运算后，此方法返回两个 BigInteger 的数组。这里，数组的第一个大整数表示除法运算的结果(this / val)，第二个大整数表示除法运算的余数(this % val)。

**语法:**

```java
public BigInteger[] divideAndRemainder(BigInteger val)
```

**参数:**该方法取 BigInteger 类型的强制参数**值**，作为除数进行除法运算。

**返回值:**这个方法返回一个两个 BigInteger 的数组，包含商(this / val)作为第一个元素，余数(this % val)作为第二个元素。

**异常:**如果参数中传入了 null 或 0，该方法将抛出**算术异常**。

**例:**

```java
Input: 42245, 23
Output: [1836, 17]

Input: 25556, 444
Output: [57, 248]

Explanation: In input two BigInteger are given.
The first one is the dividend, which calls the method,
and the second is the divisor, which is passed as parameter.
When applying division operation, as a result, 
an array of quotient and remainder is returned as output.
These are also of BigInteger type

```

下面的程序说明了 BigInteger 类的 divideAndRemainder()方法:

**程序 1:**

```java
// Java program to demonstrate divideAndRemainder() method

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger dividend = new BigInteger("25556");
        BigInteger divisor = new BigInteger("444");

        // applying divideAndRemainder() method
        BigInteger[] answers = dividend.divideAndRemainder(divisor);

        // print results
        System.out.println("Dividend : " + dividend);
        System.out.println("Divisor : " + divisor);
        System.out.println("Quotient  : " + answers[0]);
        System.out.println("Remainder : " + answers[1]);
    }
}
```

**输出:**

```java
Dividend : 25556
Divisor : 444
Quotient  : 57
Remainder : 248

```

**程序二:**

```java
// Java program to demonstrate divideAndRemainder() method

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger dividend = new BigInteger("32345678987");
        BigInteger divisor = new BigInteger("1537862842");

        // applying divideAndRemainder() method
        BigInteger[] answers = dividend.divideAndRemainder(divisor);

        // print results
        System.out.println("Dividend : " + dividend);
        System.out.println("Divisor : " + divisor);
        System.out.println("Quotient  : " + answers[0]);
        System.out.println("Remainder : " + answers[1]);
    }
}
```

**输出:**

```java
Dividend : 32345678987
Divisor : 1537862842
Quotient  : 21
Remainder : 50559305

```

**程序 3:** 演示算术异常

```java
// Java program to demonstrate divideAndRemainder() method

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger dividend = new BigInteger("32345678987");

        // Creating 0 as divisor
        BigInteger divisor = new BigInteger("0");

        // print both numbers
        System.out.println("Dividend : " + dividend);
        System.out.println("Divisor : " + divisor);

        try {
            // applying divideAndRemainder() method
            BigInteger[] answers = dividend.divideAndRemainder(divisor);

            // print results
            System.out.println("Quotient  : " + answers[0]);
            System.out.println("Remainder : " + answers[1]);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Dividend : 32345678987
Divisor : 0
Exception: java.lang.ArithmeticException: BigInteger divide by zero

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/math/big integer . html # divideanderemainder-Java . math . big integer-](https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html#divideAndRemainder-java.math.BigInteger-)