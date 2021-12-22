# Java 中的 BigDecimal byteValueExact()方法

> 原文:[https://www . geesforgeks . org/big decimal-byteevalueexact-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-bytevalueexact-method-in-java/)

**Java . math . BigDecimal . Bytevalueexact()**是一个内置函数，它将 BigDecimal 转换为一个字节，并检查丢失的信息。任何大于 127 或小于-128 的大十进制值*都将产生异常，因为它不符合字节范围。*

**语法:**

```java
public byte byteValueExact()
```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回 BigDecimal 对象的字节值。

**异常:**如果大十进制有非零小数部分，即十进制值，或者超出字节结果的可能范围，该函数抛出*算术异常*。

**示例:**

```java
Input : 127
Output : 127

Input : -67
Output : -67

```

下面的程序将说明 byteValueExact()函数的使用:
**程序 1:**

```java
// Java program to demonstrate byteValueExact() method
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigDecimal object
        BigDecimal b;

        // Creating a byte objects
        byte bt;

        b = new BigDecimal("47");

        // Assigning the byte value of b to bt
        bt = b.byteValueExact();

        // Displaying the byte value
        System.out.println("Exact byte value of " + b + " is " + bt);
    }
}
```

**Output:**

```java
Exact byte value of 47 is 47

```

**程序 2:**

```java
// Java program to demonstrate byteValueExact() method
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigDecimal object
        BigDecimal b;

        b = new BigDecimal("-128.0564000");
        System.out.println("BigDecimal value : " + b);

        long roundedValue = Math.round(b.doubleValue());
        System.out.println("Rounded value : " + roundedValue);

        // Rounding is necessary as the fractional part is not zero
        // as well as exceeding the byte range of -128 to 127
        b = new BigDecimal(roundedValue);
        System.out.println("Byte converted value : " + b.byteValueExact());
    }
}
```

**Output:**

```java
BigDecimal value : -128.0564000
Rounded value : -128
Byte converted value : -128

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # byteevalueexact()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#byteValueExact())