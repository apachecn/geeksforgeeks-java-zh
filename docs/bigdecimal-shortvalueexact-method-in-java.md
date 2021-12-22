# Java 中的 BigDecimal shortValueExact()方法

> 原文:[https://www . geesforgeks . org/big decimal-short value exact-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-shortvalueexact-method-in-java/)

**java . math . BigDecimal . short value exact()**是 Java 中的一个内置方法，它将这个 big decimal 转换成一个短整型，检查丢失的信息。如果这个大十进制有一个非零的小数部分，或者超出了短结果的可能范围，那么抛出一个算术异常。

**语法:**

```
public short shortValueExact()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回 BigDecimal 对象的短值。

以下程序说明了上述方法:
**程序 1:**

```
// Program to demonstrate shortValueExact() method of BigDecimal 

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("457");
        BigDecimal b2 = new BigDecimal("4785");

        // Assigning the short value of BigDecimal objects b1 and b2
        // to short s1, s2 respectively
        short s1 = b1.shortValueExact();
        short s2 = b2.shortValueExact();

        // Printing s1, s2 values
        System.out.println("Exact short value of " + b1 + " is " + s1);
        System.out.println("Exact short value of " + b2 + " is " + s2);
    }
}
```

**Output:**

```
Exact short value of 457 is 457
Exact short value of 4785 is 4785

```

**程序 2:**

```
// Program to demonstrate shortValueExact() method of BigDecimal 

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("127");
        BigDecimal b2 = new BigDecimal("1455");

        // assign the short value of BigDecimal objects b1 and b2
        // to short s1, s2 respectively
        short s1 = b1.shortValueExact();
        short s2 = b2.shortValueExact();

        // print s1, s2 values
        System.out.println("Exact short value of " + b1 + " is " + s1);
        System.out.println("Exact short value of " + b2 + " is " + s2);
    }
}
```

**Output:**

```
Exact short value of 127 is 127
Exact short value of 1455 is 1455

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # shortValueExact()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#shortValueExact())