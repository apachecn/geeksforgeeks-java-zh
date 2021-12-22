# Java 中 BigDecimal toBigInteger()方法

> 原文:[https://www . geesforgeks . org/big decimal-tobiginteger-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-tobiginteger-method-in-java/)

**java . math . BigDecimal . TobiginTeger()**是 Java 中的一个内置方法，可以将这个 BigDecimal 转换为 BigInteger。这种转换类似于从 double 到 long 的收缩基元转换。这个大小数的任何小数部分都将被丢弃。这种转换可能会丢失关于 BigDecimal 值精度的信息。

**注意:**如果在转换中不精确地抛出异常(换句话说，如果丢弃了非零小数部分)，请使用 toBigIntegerExact()方法。

**语法:**

```
public BigInteger toBigInteger()
```

**参数:**该方法不接受任何参数。
**返回值:**此方法返回转换为大整数的大十进制对象的值。

**示例:**

```
Input: (BigDecimal) 123.321
Output: (BigInteger) 123

Input: (BigDecimal) 123.001
Output: (BigInteger) 123
```

下面的程序说明了上述方法的工作原理:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to demonstrate toBigInteger() method of BigDecimal

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Assigning the BigDecimal b
        BigDecimal b = new BigDecimal("123.321");

        // Assigning the BigInteger value of  BigDecimal b to  BigInteger i
        BigInteger i = b.toBigInteger();

        // Print i value
        System.out.println("BigInteger value of " + b + " is " + i);
    }
}
```

**Output:** 

```
BigInteger value of 123.321 is 123
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to demonstrate toBigInteger() method of BigDecimal

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Assigning the BigDecimal b
        BigDecimal b = new BigDecimal("123.001");

        // Assigning the BigInteger value of  BigDecimal b to  BigInteger i
        BigInteger i = b.toBigInteger();

        // Printing i value
        System.out.println("BigInteger value of " + b + " is " + i);
    }
}
```

**Output:** 

```
BigInteger value of 123.001 is 123
```

**参考**:[https://docs . Oracle . com/javae/7/docs/API/Java/math/bigdecimal . html # tobiginteger()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#toBigInteger())