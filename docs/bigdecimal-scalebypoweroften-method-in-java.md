# Java 中的 BigDecimal scaleByPowerOfTen()方法

> 原文:[https://www . geesforgeks . org/big decimal-scalebypowerfresh-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-scalebypoweroften-method-in-java/)

**java . math . BigDecimal . scalebypowerfresh(*int n*)**是 Java 上的一个内置方法，它返回一个数值等于(this * 10n)的 BigDecimal。结果的等级是*(this . scale()–n)*。

**语法:**

```
public BigDecimal scaleByPowerOfTen(int n)

```

**参数:**
该方法接受整数类型的单个参数 *n* ，该参数是 BigDecimal 对象乘以 10 的幂的值。

**返回值:**这个方法返回值为这个* 10n 的 BigDecimal 对象。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program to demonstrate the
// scaleByPowerOfTen() method

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        // Assign two bigecimal objects
        BigDecimal b1 = new BigDecimal("754.000");
        BigDecimal b2 = new BigDecimal("75400");

        // Assign the result of method on b1, b2
        // to BigDecimal objects b3, b4
        BigDecimal b3 = b1.scaleByPowerOfTen(4);
        BigDecimal b4 = b2.scaleByPowerOfTen(-4);

        // Print b3, b4 values
        System.out.println(b1 + " raised to power is " + b3);
        System.out.println(b2 + " raised to power is " + b4);
    }
}
```

**Output:**

```
754.000 raised to power is 7.54000E+6
75400 raised to power is 7.5400

```

**程序 2:**

```
// Java program to demonstrate the
// scaleByPowerOfTen() method

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        // Assign two bigecimal objects
        BigDecimal b1 = new BigDecimal("200");
        BigDecimal b2 = new BigDecimal("7540000000");

        // Assign the result of method on b1, b2
        // to BigDecimal objects b3, b4
        BigDecimal b3 = b1.scaleByPowerOfTen(4);
        BigDecimal b4 = b2.scaleByPowerOfTen(-4);

        // Print b3, b4 values
        System.out.println(b1 + " raised to power is " + b3);
        System.out.println(b2 + " raised to power is " + b4);
    }
}
```

**Output:**

```
200 raised to power is 2.00E+6
7540000000 raised to power is 754000.0000

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # scalebypowerchange(int)](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#scaleByPowerOfTen(int))