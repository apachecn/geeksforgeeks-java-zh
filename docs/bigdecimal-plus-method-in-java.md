# Java 中的 BigDecimal plus()方法

> 原文:[https://www . geesforgeks . org/big decimal-plus-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-plus-method-in-java/)

1.  **java . math . BigDecimal . plus()**是 Java 中的一个内置方法，它返回一个 BigDecimal，其值为(+this)，其小数位数为 this.scale()。该方法简单地返回 BigDecimal，包含该方法是为了与一元减方法否定()保持对称。
    **语法:**

```java
public BigDecimal plus()
```

1.  **参数:**函数不接受任何参数。
    **返回值:**此方法返回对象值即此。
    以下程序说明上述方法的工作:
    **程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// plus() method

import java.math.*;

public class Gfg {

    public static void main(String[] args)
    {

        // Assign value to b1
        BigDecimal b1 = new BigDecimal("-45.652");

        // Assign the result of plus method on
        // BigDecimal Objects b1 to b2
        BigDecimal b2 = b1.plus();

        // Print the value of b2
        System.out.println("The value of the BigDecimal is " + b2);
    }
}
```

**Output:** 

```java
The value of the BigDecimal is -45.652
```

1.  **节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// plus() method

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        // Assign value to b1
        BigDecimal b1 = new BigDecimal("7458.3256");

        // Assign the result of plus method on
        // BigDecimal Objects b1 to b2
        BigDecimal b2 = b1.plus();

        // Print the value of b2
        System.out.println("The value of the BigDecimal is " + b2);
    }
}
```

**Output:** 

```java
The value of the BigDecimal is 7458.3256
```

2.  **java . math . BigDecimal . plus(math context MC)**是 Java 中的一个内置方法，它返回一个 big decimal，其值为(+this)，并根据上下文设置进行舍入。
    **语法:**

```java
public BigDecimal plus(*MathContext mc*)
```

1.  **参数:**该方法接受单个参数 *mc* ，该参数是指要使用的舍入的上下文，即该值将被舍入到的位数。
    **返回值:**该方法返回 BigDecimal Object 的值，必要时四舍五入。零结果的标度为 0。
    下面的程序说明了上述方法的工作:
    **程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// plus() method

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("-452.325");

        MathContext m = new MathContext(4); // 4 precision

        // Perform plus on BigDecimal Objects b1 using m
        BigDecimal b2 = b1.plus(m);

        // Print the value of b2
        System.out.println("Result of plus is " + b2);
    }
}
```

**Output:** 

```java
Result of plus is -452.3
```

1.  **节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// plus() method

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {

        BigDecimal b1 = new BigDecimal("-10.325");

        // 4 precision
        MathContext m = new MathContext(4);

        // Perform plus on BigDecimal Objects b1 using m
        BigDecimal b2 = b1.plus(m);

        // Print the value of b2
        System.out.println("Result of plus is " + b2);
    }
}
```

**Output:** 

```java
Result of plus is -10.33
```

参考:[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # plus()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#plus())