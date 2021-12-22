# Java 中的 BigDecimal scale()方法

> 原文:[https://www . geesforgeks . org/big decimal-scale-method in-Java/](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/)

**java . math . BigDecimal . scale()**是 Java 中的一个内置方法，它返回*这个* BigDecimal 的小数位数。

*   For *zero* or *positive* values, the scale is the number of digits to the right of the decimal point.
*   For *negative* value, the unscaled value of the number is multiplied by the negative power of the scale of ten.

**语法:**

```java
public int scale()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回这个 BigDecimal 对象的小数位数。

下面的程序说明了上述方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate the
// scale() method

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("456.0");
        BigDecimal b2 = new BigDecimal("-1.456");

        // Assign the result of scale on
        // BigDecimal Objects b1, b2 to int objects i1, i2
        int i1 = b1.scale();
        int i2 = b2.scale();

        // Print the values of i1, i2;
        System.out.println("The scale of " + b1 + " is " + i1);
        System.out.println("The scale of " + b2 + " is " + i2);
    }
}
```

**输出:**

```java
The scale of 456.0 is 1
The scale of -1.456 is 3

```

**程序二:**

```java
// Java program to demonstrate the
// scale() method

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("745");
        BigDecimal b2 = new BigDecimal("-174");

        // Assign the result of scale on
        // BigDecimal Objects b1, b2 to int objects i1, i2
        int i1 = b1.scale();
        int i2 = b2.scale();

        // Print the values of i1, i2;
        System.out.println("The scale of " + b1 + " is " + i1);
        System.out.println("The scale of " + b2 + " is " + i2);
    }
}
```

**输出:**

```java
The scale of 745 is 0
The scale of -174 is 0

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # scale()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#scale())