# Java 中的 BigDecimal sqrt()方法，带示例

> 原文:[https://www . geesforgeks . org/big decimal-sqrt-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-sqrt-method-in-java-with-examples/)

**T1。sqrt(MathContext mc)** 是在 **Java SE 9 & JDK 9** 中添加的一个内置函数，它返回一个 BigDecimal 的平方根的 BigDecimal 值，根据上下文设置，sqrt()方法在该值上应用了舍入。

**语法:**

```
public BigDecimal sqrt(MathContext mc)

```

**参数:**该方法接受 **MathContext** 类型的参数 **mc** 进行上下文设置。

**返回值:**该方法根据上下文设置，通过舍入，返回其平方根的**近似值。**

**异常:**该方法针对以下情况抛出[算法异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。

*   If the decimal number is less than zero.
*   If an accurate result is required (accuracy = 0), and the accurate result has no finite decimal expansion.
*   If the accurate result does not meet the precision figure.

**注:**此方法只在 **JDK 9** 有。

下面的程序用来说明 BigDecimal 的 sqrt()方法:

**例 1:**

```
// Java program to demonstrate sqrt() method

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigDecimal object
        BigDecimal a, squareRoot;

        a = new BigDecimal("100000000000000000000");

        // Set precision to 10
        MathContext mc
            = new MathContext(10);

        // calculate square root of bigDecimal
        // using sqrt() method
        squareRoot = a.sqrt(mc);

        // print result
        System.out.println("Square root value of " + a
                           + " is " + squareRoot);
    }
}
```

**输出:**

```
Square root value of 100000000000000000000 is 1.000000000E+10

```

**示例 2:** 显示 sqrt()方法引发的异常。

```
// Java program to demonstrate sqrt() method

import java.math.*;

class GFG {

    public static void main(String[] args)
    {

        // Creating a BigDecimal object
        BigDecimal a, squareRoot;

        a = new BigDecimal("-4");

        // Set precision to 10
        MathContext mc
            = new MathContext(10);

        // calculate square root of bigDecimal
        // using sqrt() method
        try {
            squareRoot = a.sqrt(mc);

            // print result
            System.out.println("Square root"
                               + " value of " + a
                               + " is " + squareRoot);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.lang.ArithmeticException: Attempted square root of negative BigDecimal

```

**参考文献:**[https://docs . Oracle . com/javase/9/docs/API/Java/math/bigdecimal . html # sqrt-Java . math . math context-](https://docs.oracle.com/javase/9/docs/api/java/math/BigDecimal.html#sqrt-java.math.MathContext-)