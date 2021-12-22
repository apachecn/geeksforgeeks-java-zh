# Java 中 BigDecimal toBigIntegerExact()方法

> 原文:[https://www . geesforgeks . org/big decimal-tobigintegerexact-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-tobigintegerexact-method-in-java/)

**java . math . BigDecimal . tobigintegerexact()**是 Java 中的一个内置方法，它将这个 big decimal 转换为 BigInteger，检查丢失的信息。如果这个 BigDecimal 有非零的小数部分，就会引发异常。

**语法:**

```java
public BigInteger toBigIntegerExact()

```

**参数:**该方法不取任何参数。

**返回值:**此方法返回转换为 BigInteger 的 BigDecimal 对象的值。

**示例:**

```java
Input: (BigDecimal) 1213
Output: (BigInteger) 1213

Input: (BigDecimal) 12785412
Output: (BigInteger) 12785412
```

以下程序说明了上述方法的工作:
**程序 1:**

```java
// Program to demonstrate toBigIntegerExact() method of BigDecimal 

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        // Assigning BigDecimal b
        BigDecimal b = new BigDecimal("1213");

        // Assigning the BigIntegerExact value of BigInteger b to  BigInteger  i
        BigInteger i = b.toBigIntegerExact();

        // Printing i value
        System.out.println("BigInteger value of " + b + " is " + i);
    }
}
```

**Output:**

```java
BigInteger value of 1213 is 1213

```

**程序 2:**

```java
// Program to demonstrate toBigIntegerExact() method of BigDecimal 

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        // Assigning BigDecimal b
        BigDecimal b = new BigDecimal("12785412");

        // Assigning the BigIntegerExact value of BigInteger b to  BigInteger  i
        BigInteger i = b.toBigIntegerExact();

        // Printing i value
        System.out.println("BigInteger value of " + b + " is " + i);
    }
}
```

**Output:**

```java
BigInteger value of 12785412 is 12785412

```