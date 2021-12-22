# Java 8 | BigInteger longValueExact()方法及示例

> 原文:[https://www . geesforgeks . org/Java-8-big integer-longvalueexact-method-with-examples/](https://www.geeksforgeeks.org/java-8-biginteger-longvalueexact-method-with-examples/)

**Java 8 中引入了 Java . math . big integer . longvalueexact()**。这是一个内置函数，它将 BigInteger 的值转换为 long，并检查丢失的信息。如果 BigInteger 的值大于 9，223，372，036，854，775，807 或小于-9，223，372，036，854，775，808；该方法将抛出*算术异常*，因为大整数不适合长范围。

**语法:**

```java
public long longValueExact()
```

**返回值:**这个方法返回这个 BigInteger 的长值。

**异常:**如果 BigInteger 的值大于 9，223，372，036，854，775，807 或小于-9，223，372，036，854，775，808，则方法抛出**算术异常**；因为这个范围不适合长距离。

**例:**

```java
Input: 98169894145
Output: 98169894145
Explanation: 98169894145 is given as input which is BigInteger
and long value of 98169894145 is 98169894145

Input: -65416518651
Output: -65416518651
Explanation: -65416518651 is given as input which is BigInteger 
and long value of -65416518651 is -65416518651

Input: 10000000000000000000
Output: ArithmeticException
Explanation: When 10000000000000000000 is tried to convert to long,
since 10000000000000000000 > 9,223,372,036,854,775,807 (greater than a long's range), 
therefore it throws an arithmetic exception.

```

下面的程序说明了 BigInteger 类的 longValueExact()方法:

**程序一:**演示正数<的 longValueExact()方法 9，223，372，036，854，775，807

```java
// Java program to demonstrate longValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big;
        big = new BigInteger("98169894145");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the long value
        long b1 = big.longValueExact();

        // print long value
        System.out.println("long converted value : "
                           + b1);
    }
}
```

**输出:**

```java
BigInteger value : 98169894145
long converted value : 98169894145

```

**程序二:**演示负数>的 longValueExact()方法-9，223，372，036，854，775，808

```java
// Java program to demonstrate longValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big = new BigInteger("-65416518651");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the long value
        long b1 = big.longValueExact();

        // print long value
        System.out.println("long converted value : "
                           + b1);
    }
}
```

**输出:**

```java
BigInteger value : -65416518651
long converted value : -65416518651

```

**程序 3:** 演示负数<的 longValueExact()方法-9，223，372，036，854，775，808。它会抛出算术异常

```java
// Java program to demonstrate longValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big = new BigInteger("-10000000000000000000");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the long value
            long b1 = big.longValueExact();

            // print long value
            System.out.println("long converted value : "
                               + b1);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
BigInteger value : -10000000000000000000
Exception: java.lang.ArithmeticException: BigInteger out of long range

```

**程序 4:** 演示正数>的 longValueExact()方法 9，223，372，036，854，775，807。它会抛出算术异常

```java
// Java program to demonstrate longValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big = new BigInteger("10000000000000000000");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the long value
            long b1 = big.longValueExact();

            // print long value
            System.out.println("long converted value : "
                               + b1);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
BigInteger value : 10000000000000000000
Exception: java.lang.ArithmeticException: BigInteger out of long range

```

**参考:**[https://docs . Oracle . com/javae/8/docs/API/Java/math/big integer . html # long value exact】](https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html#longValueExact--)