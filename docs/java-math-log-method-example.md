# Java Math log()方法示例

> 原文:[https://www.geeksforgeeks.org/java-math-log-method-example/](https://www.geeksforgeeks.org/java-math-log-method-example/)

**java.lang.Math.log()** 方法返回一个双精度值的自然对数(以 e 为底)作为参数。有各种情况:

*   If the argument is **nan or less than zero** , then the result is **nan** .
*   If the independent variable is **positive infinity** , then the result is **positive infinity** .
*   If the independent variable is **positive zero or negative zero** , the result is **negative infinity** .

**语法:**

```java
public static double log(double a)
```

**参数:**

```java
a : User input
```

**返回:**

```java
This method returns the value ln a.
```

**例:**展示 **java.lang.Math.log()** 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.log() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {

        double a = -2.55;
        double b = 1.0 / 0;
        double c = 0, d = 145.256;

        // negative integer as argument, output NAN
        System.out.println(Math.log(a));

        // positive infinity as argument, output Infinity
        System.out.println(Math.log(b));

        // positive zero as argument, output -Infinity
        System.out.println(Math.log(c));

        // positive double as argument
        System.out.println(Math.log(d));

    }
}
```

**输出:**

```java
NaN
Infinity
-Infinity
4.978497702968366

```