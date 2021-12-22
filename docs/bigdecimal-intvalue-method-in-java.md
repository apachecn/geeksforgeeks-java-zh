# Java 中的 BigDecimal intValue()方法

> 原文:[https://www . geesforgeks . org/big decimal-int value-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-intvalue-method-in-java/)

Java . math . BigDecimal . int value()是一个内置函数，它将*这个* BigDecimal 转换成一个整数值。该函数丢弃该大小数的任何小数部分。如果转换结果太大，无法用整数值表示，则该函数只返回低阶的 32 位。

**语法:**

```
public int intValue()
```

**参数:**此功能不接受参数。

**返回值:**该函数返回*这个*大十进制的整数值。

**示例:**

```
Input : 19878124.176
Output : 19878124

Input : "721111"
Output : 721111

```

下面的程序说明了**Java . math . bigdecimal . int value()**方法:

**程序 1:**

```
// Java program to illustrate
// intValue() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating 2 BigDecimal Objects
        BigDecimal b1, b2;
        // Assigning values to b1, b2
        b1 = new BigDecimal("19878124.176");
        b2 = new BigDecimal("721111");
        // Displaying their respective Integer Values
        System.out.println("The Integer Value of " + b1 + " is " 
                                                + b1.intValue());
        System.out.println("The Integer Value of " + b2 + " is "
                                                + b2.intValue());
    }
}
```

**输出:**

```
The Integer Value of 19878124.176 is 19878124
The Integer Value of 721111 is 721111

```

**注意:**关于大*的整体幅度和精度的信息，该*大十进制值可能会在该函数的转换过程中丢失。因此，可能会返回符号相反的结果。

**程序 2:** 该程序说明了函数返回符号相反的结果的场景。

```
// Java program to illustrate
// intValue() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating 2 BigDecimal Objects
        BigDecimal b1, b2;
        // Assigning values to b1, b2
        b1 = new BigDecimal("1987812417600");
        b2 = new BigDecimal("3567128439701");
        // Displaying their respective Integer Values
        System.out.println("The Integer Value of " + b1 + " is " + b1.intValue());
        System.out.println("The Integer Value of " + b2 + " is " + b2.intValue());
    }
}
```

**输出:**

```
The Integer Value of 1987812417600 is -757440448
The Integer Value of 3567128439701 is -1989383275

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # int value()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#intValue())