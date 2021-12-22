# 带示例的 Java 数学 exp()方法

> 原文:[https://www.geeksforgeeks.org/java-math-exp-method-example/](https://www.geeksforgeeks.org/java-math-exp-method-example/)

**java.lang.Math.exp()** 返回欧拉数 e 的二次幂。

*   如果论证是 **NaN** ，那么结果就是 **NaN** 。
*   如果参数是**正无穷大**，那么结果就是**正无穷大**。
*   如果参数为**负无穷大**，那么结果为**正零**。

**语法:**

```java
public static double exp(double a)
Parameter : 
a : the exponent part which raises to e. 

```

**返回:**
值 e <sup>a</sup> ，其中 e 是自然对数的基数。

**示例:**展示 java.lang.Math.exp()函数的工作原理

```java
// Java program to demonstrate working
// of java.lang.Math.exp() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double x = 3;

        // when both are not infinity
        double result = Math.exp(x);
        System.out.println(result);

        double positiveInfinity = 
               Double.POSITIVE_INFINITY;
        double negativeInfinity = 
               Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;

        // when 1 is NAN
        result = Math.exp(nan);
        System.out.println(result);

        // when one argument is +INF
        result = Math.exp(positiveInfinity);
        System.out.println(result);

        result = Math.exp(negativeInfinity);
        System.out.println(result);
    }
}
```

**Output:**

```java
20.085536923187668
NaN
Infinity
0.0

```