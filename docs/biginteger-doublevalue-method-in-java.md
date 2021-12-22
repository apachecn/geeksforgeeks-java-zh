# Java 中的 BigInteger doubleValue()方法

> 原文:[https://www . geesforgeks . org/big integer-double value-method-in-Java/](https://www.geeksforgeeks.org/biginteger-doublevalue-method-in-java/)

**Java . math . BigInteger . Double VaLue()**将这个 BigInteger 转换成一个双精度值。如果此函数返回的值太大，无法用双精度表示，那么它将被转换为双精度。负无穷大或双精度。视情况而定，正值 _ 无穷大。这种转换可能会丢失关于 BigInteger 值精度的信息。

**语法:**

```
public double doubleValue()
```

**返回值:**该方法返回一个双精度值，该值代表该大整数的双精度值。

**示例:**

```
Input: BigInteger1=32145
Output: 32145.0
Explanation: BigInteger1.doubleValue()=32145.0.

Input: BigInteger1=32145535361361525377
Output: 3.2145535E19
Explanation: BigInteger1.doubleValue()=3.2145535E19\. This BigInteger is too big for 
a magnitude to represent as a double then it will be converted to Double.NEGATIVE_INFINITY 
or Double.POSITIVE_INFINITY as appropriate.

```

下面的程序说明了 BigInteger 类的 doubleValue()方法:

**例 1:**

```
// Java program to demonstrate doubleValue() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("32145");
        b2 = new BigInteger("7613721");

        // apply doubleValue() method
        double doubleValueOfb1 = b1.doubleValue();
        double doubleValueOfb2 = b2.doubleValue();

        // print doubleValue
        System.out.println("doubleValue of " + b1 + " : " + doubleValueOfb1);
        System.out.println("doubleValue of " + b2 + " : " + doubleValueOfb2);
    }
}
```

**输出:**

```
doubleValue of 32145 : 32145.0
doubleValue of 7613721 : 7613721.0

```

**示例 2:** 当返回的双精度值太大，无法用双精度值表示时。

```
// Java program to demonstrate doubleValue() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("32145535361361525377");
        b2 = new BigInteger("7613721535372632367351");

        // apply doubleValue() method
        double doubleValueOfb1 = b1.doubleValue();
        double doubleValueOfb2 = b2.doubleValue();

        // print doubleValue
        System.out.println("doubleValue of " + b1 + " : " + doubleValueOfb1);
        System.out.println("doubleValue of " + b2 + " : " + doubleValueOfb2);
    }
}
```

**输出:**

```
doubleValue of 32145535361361525377 : 3.2145535361361527E19
doubleValue of 7613721535372632367351 : 7.613721535372632E21

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # double value()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#doubleValue())