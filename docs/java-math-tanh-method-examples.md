# Java 数学 tanh()方法示例

> 原文:[https://www . geesforgeks . org/Java-math-tanh-method-examples/](https://www.geeksforgeeks.org/java-math-tanh-method-examples/)

**java.lang.Math.tanh()** 返回作为参数传递给它的双曲正切值。任何值 *a* 的双曲正切定义为:

((e<sup>a</sup>–e<sup>-a</sup>)/2)/((e<sup>a</sup>+e<sup>-a</sup>)/2)

其中 e 是欧拉数。换句话说，我们可以说 tanh(a) = sinh(a)/cosh(a)。

如果参数是 **NaN** ，那么结果就是 **NaN** 。如果参数是**正无穷大**，那么结果将是 **+1.0** 。如果参数为**负无穷大**，则结果为 **-1.0** 。如果自变量为**零**，则结果为**零**，符号与自变量 a 相同。

**语法:**

```
public static double tanh(double a)
Parameter :
a : the value whose hyperbolic tangent is to be returned.

```

**返回:**
此方法返回参数的**双曲正切**值。

**例 1 :** 展示 **java.lang.Math.tanh()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.tanh() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {

        double a = 3.5;

        System.out.println(Math.tanh(a));

        a = 90.328;

        System.out.println(Math.tanh(a));

        a = 0;
        // argument is zero, output will also be 0
        System.out.println(Math.tanh(a));
    }
}
```

**Output:**

```
0.9981778976111987
1.0
0.0

```

**例 2 :** 展示当自变量为 NaN 或无穷大时 **java.lang.Math.tanh()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.tanh() method infinity case
import java.lang.Math; // importing java.lang package

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
        result = Math.tanh(negativeInfinity);
        System.out.println(result);

        // Here argument is positive infinity
        result = Math.tanh(positiveInfinity);
        System.out.println(result);

        // Here argument is NaN, output will be NaN
        result = Math.tanh(nan);
        System.out.println(result);
    }
}
```

**Output:**

```
-1.0
1.0
NaN

```