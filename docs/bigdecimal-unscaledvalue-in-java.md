# Java 中的 BigDecimal unscaledValue()

> 原文:[https://www . geesforgeks . org/big decimal-unscaled value-in-Java/](https://www.geeksforgeeks.org/bigdecimal-unscaledvalue-in-java/)

**java . math . BigDecimal . Scaled value()**是 Java 中的一个内置方法，它返回一个 BigInteger，其值是 BigDecimal 值的未缩放值。该值计算(此* 10this.scale())。

**语法:**

```java
public BigInteger unscaledValue()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个 BigInteger，它的值是这个 BigDecimal 值的未缩放值。

下面的程序说明了 BigDecimal.unscaledValue()方法:
**程序 1:**

```java
// Program to illustrate unscaledValue() method of BigDecimal 

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger i1, i2;

        BigDecimal b1 = new BigDecimal("175.856");
        BigDecimal b2 = new BigDecimal("-275.73");

        // Assigning unscaledValue of BigDecimal objects b1, b2 to i1, i2
        i1 = b1.unscaledValue();
        i2 = b2.unscaledValue();

        // Printing i1, i2 values
        System.out.println("The Unscaled Value of " + b1 + " is " + i1);
        System.out.println("The Unscaled Value of " + b2 + " is " + i2);
    }
}
```

**Output:**

```java
The Unscaled Value of 175.856 is 175856
The Unscaled Value of -275.73 is -27573

```

**程序 2:**

```java
// Program to illustrate unscaledValue() method of BigDecimal 

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger i1, i2;

        BigDecimal b1 = new BigDecimal("5.5");
        BigDecimal b2 = new BigDecimal("-2.73");

        // Assigning unscaledValue of BigDecimal objects b1, b2 to i1, i2
        i1 = b1.unscaledValue();
        i2 = b2.unscaledValue();

        // Printing i1, i2 values
        System.out.println("The Unscaled Value of " + b1 + " is " + i1);
        System.out.println("The Unscaled Value of " + b2 + " is " + i2);
    }
}
```

**Output:**

```java
The Unscaled Value of 5.5 is 55
The Unscaled Value of -2.73 is -273

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # scaleled value()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#unscaledValue())