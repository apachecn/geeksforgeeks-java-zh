# Java 数学 sinh()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-math-sinh-method-examples/](https://www.geeksforgeeks.org/java-math-sinh-method-examples/)

**java.lang.Math.sinh()** 返回作为参数传递给它的双曲正弦值。任何值的双曲正弦 *a* 定义为:

(e<sup>a</sup>–e<sup>-a</sup>)/2

其中 e 是欧拉数。

如果参数是 NaN，那么结果就是 NaN。如果自变量是无穷大，那么结果也将是无穷大，符号与自变量相同。如果该参数为零，则结果是一个零，其符号与该参数相同。

**语法:**

```
public static double sinh(double a)
Parameter :
a : the value whose hyperbolic sine is to be returned.

```

**返回:**
这个方法返回参数的双曲正弦值。

**例 1 :** 展示 **java.lang.Math.sinh()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.sinh() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {

        double a = 3.5;

        System.out.println(Math.sinh(a));

        a = 90.328;

        System.out.println(Math.sinh(a));
    }
}
```

**Output:**

```
16.542627287634996
8.470751974588509E38

```

**例 2 :** 展示当自变量为 NaN 或无穷大时 **java.lang.Math.sinh()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.sinh() method infinity case
import java.lang.Math;

public class GFG {

    // Driver code
    public static void main(String[] args)
    {

        double positiveInfinity = 
               Double.POSITIVE_INFINITY;
        double negativeInfinity = 
               Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;
        double result;

        // Here argument is negative infinity,
        // output will be negative infinity
        result = Math.sinh(negativeInfinity);
        System.out.println(result);

        // Here argument is positive infinity,
        // output will also be positive infinity
        result = Math.sinh(positiveInfinity);
        System.out.println(result);

        // Here argument is NaN, output will be NaN
        result = Math.sinh(nan);
        System.out.println(result);
    }
}
```

**Output:**

```
-Infinity
Infinity
NaN

```