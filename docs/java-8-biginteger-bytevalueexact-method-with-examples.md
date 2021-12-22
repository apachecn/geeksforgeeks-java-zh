# Java 8 | BigInteger byteevalueexact()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-8-big integer-byteevalueexact-method-with-examples/](https://www.geeksforgeeks.org/java-8-biginteger-bytevalueexact-method-with-examples/)

**Java 8 中引入了 Java . math . big integer . byteevalueexact()**。这是一个内置函数，它将 BigInteger 的值转换为一个字节，并检查任何丢失的信息。如果大整数的值大于 127 或小于-128，该方法将抛出*算术异常*，因为大整数不适合字节范围。

**语法:**

```
public byte byteValueExact()
```

**返回值:**这个方法返回这个 BigInteger 的字节值。

**异常:**如果 BigInteger 的值大于 127 或小于-128，该方法将抛出**算术异常**，因为该范围不适合字节范围。

**例:**

```
Input: 122
Output: 122
Explanation: 122 is given as input which is bigInteger
and byte value of 122 is 122

Input: -46
Output: -46
Explanation: -46 is given as input which is bigInteger 
and byte value of -46 is -46

Input: 200
Output: ArithmeticException
Explanation: When 200 is tried to convert to Byte,
since 200 > 127 (greater than a Byte's range), 
therefore it throws an arithmetic exception.

```

下面的程序说明了 BigInteger 类的 byteValueExact()方法:

**程序 1:** 演示正数<127

```
// Java program to demonstrate byteValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big;
        big = new BigInteger("122");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the byte value
        byte b1 = big.byteValueExact();

        // print byte value
        System.out.println("Byte converted value : "
                           + b1);
    }
}
```

T5】的 byteValueExact()方法输出:

```
BigInteger value : 122
Byte converted value : 122

```

**程序二:**演示负数> -128

```
// Java program to demonstrate byteValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big = new BigInteger("-46");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the byte value
        byte b1 = big.byteValueExact();

        // print byte value
        System.out.println("Byte converted value : "
                           + b1);
    }
}
```

**的 byteValueExact()方法输出:**

```
BigInteger value : -46
Byte converted value : -46

```

**程序 3:** 演示负数< -128 的 byteValueExact()方法。它会抛出算术异常

```
// Java program to demonstrate byteValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big = new BigInteger("-200");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the byte value
            byte b1 = big.byteValueExact();

            // print byte value
            System.out.println("Byte converted value : "
                               + b1);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
BigInteger value : -200
Exception: java.lang.ArithmeticException: BigInteger out of byte range

```

**程序 4:** 演示正数> 127 的 byteValueExact()方法。它会抛出算术异常

```
// Java program to demonstrate byteValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big = new BigInteger("200");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the byte value
            byte b1 = big.byteValueExact();

            // print byte value
            System.out.println("Byte converted value : "
                               + b1);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
BigInteger value : 200
Exception: java.lang.ArithmeticException: BigInteger out of byte range

```

**参考:**[https://docs . Oracle . com/javae/8/docs/API/Java/math/big integer . html # bytevalueexact】](https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html#byteValueExact--)