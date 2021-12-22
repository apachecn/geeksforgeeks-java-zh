# Java 中的 BigDecimal ulp()方法

> 原文:[https://www . geesforgeks . org/big decimal-ulp-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-ulp-method-in-java/)

**java . math . BigDecimal . ulp()**是 Java 中的一个内置方法，它返回这个 BigDecimal 的 ulp(最后一位的单位)的大小。

*   非零大十进制值的 ulp 被定义为该值与大十进制值之间的正距离，大十进制值在数量上比大十进制值大，位数相同。
*   一个零值的 ulp 在数值上等于 1。结果以与此相同的比例存储，因此零值和非零值的结果等于[1，this.scale()]。

**语法:**

```
public BigDecimal ulp()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个大十进制的 ulp 的大小。

**示例:**

```
Input: 4.25
Output: 0.01

Input: 1789
Output: 1
```

以下程序说明了上述方法:
**程序 1:**

```
// Program to illustrate the ulp() method of BigDecimal 

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        // Assigning BigDecimal object
        BigDecimal b1 = new BigDecimal("1789");
        BigDecimal b2 = new BigDecimal("4.25");

        // Assigning ulp value of BigDecimal object b1, b2 to b3, b4
        BigDecimal b3 = b1.ulp();
        BigDecimal b4 = b2.ulp();

        // Printing b3, b4 values
        System.out.println("ULP value of " + b1 + " is " + b3);
        System.out.println("ULP value of " + b2 + " is " + b4);
    }
}
```

**Output:**

```
ULP value of 1789 is 1
ULP value of 4.25 is 0.01

```

**程序 2:**

```
// Program to illustrate the ulp() method of BigDecimal 

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        // Assigning BigDecimal object
        BigDecimal b1 = new BigDecimal("78645");
        BigDecimal b2 = new BigDecimal("4.252547");

        // Assign ulp value of BigDecimal object b1, b2 to b3, b4
        BigDecimal b3 = b1.ulp();
        BigDecimal b4 = b2.ulp();

        // Printing b3, b4 values
        System.out.println("ULP value of " + b1 + " is " + b3);
        System.out.println("ULP value of " + b2 + " is " + b4);
    }
}
```

**Output:**

```
ULP value of 78645 is 1
ULP value of 4.252547 is 0.000001

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # ulp()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#ulp())