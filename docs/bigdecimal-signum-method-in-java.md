# Java 中的 BigDecimal signum()方法

> 原文:[https://www . geesforgeks . org/big decimal-signum-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-signum-method-in-java/)

**java . math . BigDecimal . signum()**是 Java 中的一个内置方法，它返回这个 BigDecimal 的 signum 函数。符号函数或符号函数是提取实数符号的奇数数学函数。在数学表达式中，符号函数通常表示为 sgn。

**语法:**

```java
public int signum()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法可以返回三种类型的值:

*   如果此大十进制数< 0，则为-1
*   如果此 BigDecimal = 0，则为 0
*   1 如果这个大十进制大于 0

下面的程序说明了上述方法的工作原理:

**程序 1:**

```java
// Program to demonstrate signum() method of BigDecimal 

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("12743");
        BigDecimal b2 = new BigDecimal("0");
        BigDecimal b3 = new BigDecimal("-4512");

        // Assigning the signum values of  BigDecimal objects b1, b2, b3
        // to  int objects i1, i2, i3 respectively
        int i1 = b1.signum();
        int i2 = b2.signum();
        int i3 = b3.signum();

        // Printing i1, i2, i3 values
        System.out.println("Signum function on " + b1 + " is " + i1);
        System.out.println("Signum function on " + b2 + " is " + i2);
        System.out.println("Signum function on " + b3 + " is " + i3);
    }
}
```

**输出:**

```java
Signum function on 12743 is 1
Signum function on 0 is 0
Signum function on -4512 is -1

```

**程序二:**

```java
// Program to demonstrate signum() method of BigDecimal 

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("17845452743");
        BigDecimal b2 = new BigDecimal("000");
        BigDecimal b3 = new BigDecimal("-444512");

        // Assigning the signum values of  BigDecimal objects b1, b2, b3
        // to  int objects i1, i2, i3 respectively
        int i1 = b1.signum();
        int i2 = b2.signum();
        int i3 = b3.signum();

        // Printing i1, i2, i3 values
        System.out.println("Signum function on " + b1 + " is " + i1);
        System.out.println("Signum function on " + b2 + " is " + i2);
        System.out.println("Signum function on " + b3 + " is " + i3);
    }
}
```

**输出:**

```java
Signum function on 17845452743 is 1
Signum function on 0 is 0
Signum function on -444512 is -1

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # signum()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#signum())