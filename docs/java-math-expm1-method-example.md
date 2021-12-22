# Java Math expm1()方法搭配示例

> 原文:[https://www . geesforgeks . org/Java-math-ex pm1-method-example/](https://www.geeksforgeeks.org/java-math-expm1-method-example/)

Java . lang . math . ex pm1()返回 **e <sup>x</sup> -1。**注意，对于接近 0 的 x 的值，expm1(x) + 1 的精确和比 exp(x)更接近 e <sup>x</sup> 的真实结果。

*   如果论证是 **NaN，**的结果是 **NaN。**
*   如果参数是**正无穷大，**则结果是**正无穷大。**
*   如果参数为**负无穷大，**则结果为 **-1.0。**
*   如果参数是**零，**则结果是一个零，其符号与参数相同。

**语法:**

```java
public static double expm1(double x) 
Parameter: 
x-the exponent part which raises to e. 
```

**返回:**
该方法返回值 **e <sup>x</sup> -1** ，其中 e 是自然对数的基数。

**示例:**展示**函数的工作**

```java
// Java program to demonstrate working
// of java.lang.Math.expm1() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double x = 3;

        // when both are not infinity
        double result = Math.expm1(x);
        System.out.println(result);

        double positiveInfinity = Double.POSITIVE_INFINITY;
        double negativeInfinity = Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;

        // when x is NAN
        result = Math.expm1(nan);
        System.out.println(result);

        // when argument is +INF
        result = Math.expm1(positiveInfinity);
        System.out.println(result);

        // when  argument is -INF
        result = Math.expm1(negativeInfinity);
        System.out.println(result);

        x = -0;
        result = Math.expm1(x);
        // same sign as 0
        System.out.println(result);
    }
}
```

**输出:**

```java
19.085536923187668
NaN
Infinity
-1.0
0.0

```