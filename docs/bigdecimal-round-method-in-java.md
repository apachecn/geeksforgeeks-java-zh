# Java 中的 BigDecimal round()方法

> 原文:[https://www . geesforgeks . org/big decimal-round-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-round-method-in-java/)

**java . math . BigDecimal . round(*MathContext m*)**是 Java 中的一个内置方法，它返回一个根据 math context 设置舍入的 BigDecimal 值。如果精度设置为 0，则不进行舍入。

**语法:**

```
public BigDecimal round(*MathContext m*)

```

**参数:**该方法接受单个参数 *m* ，该参数是指要使用的上下文，即大十进制值要舍入到的值。

**返回值:**该方法根据 MathContext 设置返回一个四舍五入的 BigDecimal。

以下程序说明了 Java . math . bigdecimal . round(*math context m*)方法:
**程序 1:**

```
// Java program to demonstrate the
// round() method
import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {
        // Assign value to BigDecimal object b1
        BigDecimal b1 = new BigDecimal("4.2585");

        MathContext m = new MathContext(4); // 4 precision

        // b1 is rounded using m
        BigDecimal b2 = b1.round(m);

        // Print b2 value
        System.out.println("The value of " + b1 + 
        " after rounding is " + b2);
    }
}
```

**Output:**

```
The value of 4.2585 after rounding is 4.259

```

**程序 2:**

```
// Java program to demonstrate the
// round() method
import java.math.*;

public class gfg {

    public static void main(String[] args)
    {
        // Assigning value to BigDecimal object b1
        BigDecimal b1 = new BigDecimal("-4.2585");

        MathContext m = new MathContext(4); // 4 precision

        // b1 is rounded using m
        BigDecimal b2 = b1.round(m);

        // Print b2 value
        System.out.println("The value of " + b1 + 
        " after rounding is " + b2);
    }
}
```

**Output:**

```
The value of -4.2585 after rounding is -4.259

```

参考:[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # round(Java . math . math context)](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#round(java.math.MathContext))