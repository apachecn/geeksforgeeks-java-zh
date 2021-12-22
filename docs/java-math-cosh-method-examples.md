# Java 数学 cosh()方法示例

> 原文:[https://www . geesforgeks . org/Java-math-cosh-method-examples/](https://www.geeksforgeeks.org/java-math-cosh-method-examples/)

**java.lang.Math.cosh()** 返回作为参数传递给它的双曲余弦值。任何值的双曲余弦 *a* 定义为:

(e <sup>a</sup> + e <sup>-a</sup> )/2

其中 e 是欧拉数。

如果参数是 NaN，那么结果就是 NaN。如果参数是无穷大，那么结果将是正无穷大。如果参数为零，那么结果就是一。

**语法:**

```
public static double cosh(double a)
Parameter : 
a : the value whose hyperbolic cosine is to be returned.

```

**返回:**
这个方法返回参数的双曲余弦值。

**例 1 :** 展示 **java.lang.Math.cosh()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.cosh() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {

        double a = 3.5;

        System.out.println(Math.cosh(a));

        a = 90.328;

        System.out.println(Math.cosh(a));
    }
}
```

**Output:**

```
16.572824671057315
8.470751974588509E38

```

**例 2 :** 展示参数为 NaN 或无穷大时 **java.lang.Math.cosh()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.cosh() method infinity case
import java.lang.Math;

public class GFG {
    public static void main(String[] args)
    {

        double positiveInfinity = 
               Double.POSITIVE_INFINITY;
        double negativeInfinity = 
               Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;
        double result;

        // Here argument is negative infinity
        result = Math.cosh(negativeInfinity);
        System.out.println(result);

        // Here argument is positive infinity
        result = Math.cosh(positiveInfinity);
        System.out.println(result);

        // Here argument is NaN, output will be NaN
        result = Math.cosh(nan);
        System.out.println(result);
    }
}
```

**Output:**

```
Infinity
Infinity
NaN

```