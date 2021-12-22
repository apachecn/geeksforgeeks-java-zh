# Java 中的 BigDecimal stripTrailingZeros()方法

> 原文:[https://www . geeksforgeeks . org/big decimal-strippetrailingeros-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-striptrailingzeros-method-in-java/)

**java . math . BigDecimal . striptrailingeros()**是 Java 中的一个内置方法，它返回一个 BigDecimal，该 BigDecimal 在数字上等于这个值，但是从表示中删除了任何尾随零。因此，基本上，该函数从大十进制值中剔除尾随零。

**语法:**

```
public BigDecimal stripTrailingZeros()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个等于 BigDecimal 的数值，并去掉所有尾随零。

**示例:**

```
Input: 785.000
Output: 785

Input: 125500000
Output: 1.255E+8
```

以下程序说明了上述方法的工作:
**程序 1:**

```
// Program to demonstrate stripTrailingZeros() method of BigDecimal 

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("785.000");
        BigDecimal b2 = new BigDecimal("125500");

        // Assigning the result of stripTrailingZeros method
        // to BigDecimal objects b3, b4
        BigDecimal b3 = b1.stripTrailingZeros();
        BigDecimal b4 = b2.stripTrailingZeros();

        // print b3, b4 values
        System.out.println(b1 + " after removing trailing zeros " + b3);
        System.out.println(b2 + " after removing trailing zeros " + b4);
    }
}
```

**Output:**

```
785.000 after removing trailing zeros 785
125500 after removing trailing zeros 1.255E+5

```

**程序 2:**

```
// Program to demonstrate stripTrailingZeros() method of BigDecimal 

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("785.00000");
        BigDecimal b2 = new BigDecimal("125500000");

        // Assigning the result of stripTrailingZeros method
        // to BigDecimal objects b3, b4
        BigDecimal b3 = b1.stripTrailingZeros();
        BigDecimal b4 = b2.stripTrailingZeros();

        // Printing b3, b4 values
        System.out.println(b1 + " after removing trailing zeros " + b3);
        System.out.println(b2 + " after removing trailing zeros " + b4);
    }
}
```

**Output:**

```
785.00000 after removing trailing zeros 785
125500000 after removing trailing zeros 1.255E+8

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # stripteralingeros()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#stripTrailingZeros())