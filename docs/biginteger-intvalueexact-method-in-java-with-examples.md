# Java 中的大整数 intValueExact()方法，带示例

> 原文:[https://www . geesforgeks . org/big integer-int value exact-method-in-Java-with-examples/](https://www.geeksforgeeks.org/biginteger-intvalueexact-method-in-java-with-examples/)

**Java . math . big integer . intvalueexact()**是在 Java 8 中引入的。这是一个内置函数，它将 BigInteger 的值转换为 int，并检查丢失的信息。如果 BigInteger 的值大于 2，147，483，647 或小于-2，147，483，648；该方法将抛出*算术异常*，因为大整数不适合整数范围。

**语法:**

```java
public int intValueExact()
```

**返回值:**这个方法返回这个 BigInteger 的 int 值。

**异常:**如果 BigInteger 的值大于 2，147，483，647 或小于-2，147，483，648，则方法抛出**算术异常**；因为这个范围不适合 int 范围。

**例:**

```java
Input: 4561561
Output: 4561561
Explanation: 4561561 is given as input which is bigInteger
and int value of 4561561 is 4561561

Input: -8546512
Output: -8546512
Explanation: -8546512 is given as input which is bigInteger 
and int value of -8546512 is -8546512

Input: 3000000000
Output: ArithmeticException
Explanation: When 3000000000 is tried to convert to int,
since 3000000000 > 2,147,483,647 (greater than a int's range), 
therefore it throws an arithmetic exception.

```

下面的程序说明了 BigInteger 类的 intValueExact()方法:

**程序 1:** 演示正数< 2，147，483，647

```java
// Java program to demonstrate intValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big;
        big = new BigInteger("4561561");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the int value
        int b1 = big.intValueExact();

        // print int value
        System.out.println("int converted value : "
                           + b1);
    }
}
```

**的 intValueExact()方法输出:**

```java
BigInteger value : 4561561
int converted value : 4561561

```

**程序二:**演示负数> -2，147，483，648

```java
// Java program to demonstrate intValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big = new BigInteger("-8546512");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the int value
        int b1 = big.intValueExact();

        // print int value
        System.out.println("int converted value : "
                           + b1);
    }
}
```

**的 intValueExact()方法输出:**

```java
BigInteger value : -8546512
int converted value : -8546512

```

**程序 3:** 演示负数<的 intValueExact()方法-2，147，483，648。它会抛出算术异常

```java
// Java program to demonstrate intValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big = new BigInteger("-3000000000");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the int value
            int b1 = big.intValueExact();

            // print int value
            System.out.println("int converted value : "
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
BigInteger value : -3000000000
Exception: java.lang.ArithmeticException: BigInteger out of int range

```

**程序 4:** 演示正数> 2，147，483，647 的 intValueExact()方法。它会抛出算术异常

```java
// Java program to demonstrate intValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big = new BigInteger("3000000000");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the int value
            int b1 = big.intValueExact();

            // print int value
            System.out.println("int converted value : "
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
BigInteger value : 3000000000
Exception: java.lang.ArithmeticException: BigInteger out of int range

```

**参考:**[https://docs . Oracle . com/javae/8/docs/API/Java/math/biginteger . html # intvalueexact】](https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html#intValueExact--)