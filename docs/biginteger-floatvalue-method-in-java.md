# Java 中的大整数浮点值()方法

> 原文:[https://www . geesforgeks . org/big integer-float value-method-in-Java/](https://www.geeksforgeeks.org/biginteger-floatvalue-method-in-java/)

**Java . math . BigInteger . float VaLue()**将这个 BigInteger 转换成一个浮点值。如果这个函数返回的值对于一个数值来说太大而不能表示为浮点数，那么它将被转换为浮点数。负无穷大或浮动。视情况而定，正值 _ 无穷大。这种转换可能会丢失关于 BigInteger 值精度的信息。

**语法:**

```java
public float floatValue()
```

**返回:**该方法返回一个浮点值，代表这个大整数的浮点值。

**示例:**

```java
Input: BigInteger1=32145
Output: 32145.0
Explanation: BigInteger1.floatValue()=32145.0.

Input: BigInteger1=32145535361361525377
Output: 3.2145535E19
Explanation: BigInteger1.floatValue()=3.2145535E19\. This BigInteger is too big 
for a magnitude to represent as a float then it will be converted to 
Float.NEGATIVE_INFINITY or Float.POSITIVE_INFINITY as appropriate.

```

下面的程序说明了 BigInteger 类的 floatValue()方法:

**例 1:**

```java
// Java program to demonstrate floatValue() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("32145");
        b2 = new BigInteger("7613721");

        // apply floatValue() method
        float floatValueOfb1 = b1.floatValue();
        float floatValueOfb2 = b2.floatValue();

        // print floatValue
        System.out.println("floatValue of "
                           + b1 + " : " + floatValueOfb1);
        System.out.println("floatValue of "
                           + b2 + " : " + floatValueOfb2);
    }
}
```

**输出:**

```java
floatValue of 32145 : 32145.0
floatValue of 7613721 : 7613721.0

```

**例 2:当返回浮动太大，无法用一个量级表示为一个浮动时。**

```java
// Java program to demonstrate floatValue() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {
        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("32145535361361525377");
        b2 = new BigInteger("7613721535372632367351");

        // apply floatValue() method
        float floatValueOfb1 = b1.floatValue();
        float floatValueOfb2 = b2.floatValue();

        // print floatValue
        System.out.println("floatValue of "
                           + b1 + " : " + floatValueOfb1);
        System.out.println("floatValue of "
                           + b2 + " : " + floatValueOfb2);
    }
}
```

**输出:**

```java
floatValue of 32145535361361525377 : 3.2145535E19
floatValue of 7613721535372632367351 : 7.6137214E21

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # float value()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#floatValue())