# Java 中的 BigDecimal pow()方法，示例

> 原文:[https://www . geesforgeks . org/big decimal-pow-in-Java-method-with-examples/](https://www.geeksforgeeks.org/bigdecimal-pow-method-in-java-with-examples/)

**T1。幂(int n)** 方法用于计算一个大十进制数，该数是作为参数(this) <sup>n</sup> 传递的某个其他正数的幂。此方法执行将此大十进制数提升为作为参数传递的正数的幂。

**语法:**

```java
public BigDecimal pow(int n)

```

**参数:**这个方法接受一个参数 **n** ，这个参数是我们要把大十进制数的幂提高到的指数。

**返回:**该方法返回一个大十进制数，等于(this) <sup>n</sup> 。

**异常:**参数 n 必须在 0 到 999999999 范围内，否则抛出**算术异常**

下面的程序说明了 BigDecimal 类的 pow()方法

**例 1:**

```java
// Java program to demonstrate
// pow() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // Creating BigDecimal object
        BigDecimal b1
            = new BigDecimal("924567");

        // Exponent or power
        int n = 5;

        // Using pow() method
        BigDecimal result = b1.pow(n);

        // Display result
        System.out.println("Result of pow operation "
                           + "between BigDecimal "
                           + b1 + " and exponent "
                           + n + " equal to "
                           + result);
    }
}
```

**输出:**

> BigDecimal 924567 和等于 675603579456764176151564447607 的指数 5 之间的幂运算结果

**例 2:**

```java
// Java program to demonstrate
// pow() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // Creating BigDecimal object
        BigDecimal b1
            = new BigDecimal("457863");

        // Exponent or power
        int n = 4;

        // Using pow() method
        BigDecimal result = b1.pow(n);

        // Display result
        System.out.println("Result of pow operation "
                           + "between BigDecimal "
                           + b1 + " and exponent "
                           + n + " equal to "
                           + result);
    }
}
```

**输出:**

> BigDecimal 457863 和等于 43948311905876729579361

的指数 4 之间的幂运算结果

**示例 3:** 当作为参数传递的指数小于零时显示异常的程序。

```java
// Java program to demonstrate
// pow() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // Creating BigDecimal object
        BigDecimal b1
            = new BigDecimal("10000");

        // Negative power
        int n = -1;

        try {
            // Using pow() method
            BigDecimal result = b1.pow(n);

            // Display result
            System.out.println("Result of pow operation "
                               + "between BigDecimal "
                               + b1 + " and exponent "
                               + n + " equal to "
                               + result);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

> 异常:无效操作

**参考:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # pow(int)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#pow(int))