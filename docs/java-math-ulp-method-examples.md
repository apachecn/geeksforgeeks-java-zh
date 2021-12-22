# Java 数学 ulp()方法示例

> 原文:[https://www . geesforgeks . org/Java-math-ulp-method-examples/](https://www.geeksforgeeks.org/java-math-ulp-method-examples/)

**java.lang.Math.ulp()** 是一个内置的 java 方法，它返回参数的 ulp 大小。ulp 代表最不精确的单位。它计算给定的双精度或浮点值和下一个更大的 T2 双精度或浮点值之间的距离。
参数可以有两种类型:

*   **ulp(float f) :** 为浮点型输入。
*   **ulp(double d) :** 它接受 double 类型的输入。

**注:**

*   如果参数是 NaN，输出就是 NaN。
*   如果参数是正或负的双精度值或浮点值，则 ulp(-arg)和 ulp(arg)的输出相同。
*   如果参数为正或负零，输出将为双精度。最小值或浮动值。最小值。
*   如果参数为正无穷大或负无穷大，则输出为正无穷大。
*   如果参数为正或负，则为双精度。最大值或浮动。MAX_VALUE，双型输出为 2 <sup>971</sup> ，浮动型输出为 2 <sup>104</sup> 。

**语法:**

```
public static dataType ulp(dataType g)
Parameter :
 g: argument whose ulp is to be returned.
Return :
This method returns the size of an ulp of the argument.
```

**示例:**展示 **java.lang.Math.ulp()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.ulp() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = 34.543;

        // Input positive double value
        // Output ulp(a)
        System.out.println(Math.ulp(a));

        // Input negative double value
        // Output ulp(-a)==ulp(a)
        System.out.println(Math.ulp(-a));

        double b = 0.0 / 0;

        // Input NaN, Output Nan
        System.out.println(Math.ulp(b));

        float c = -0.0f;

        // Input negative zero
        // Output  Float.MIN_VALUE.
        System.out.println(Math.ulp(c));

        float d = -1.0f / 0;

        // Input negative infinity
        // Output  positive infinity.
        System.out.println(Math.ulp(d));

        double e = Double.MAX_VALUE;

        System.out.println(Math.ulp(e));
    }
}
```

**输出:**

```
7.105427357601002E-15
7.105427357601002E-15
NaN
1.4E-45
Infinity
1.9958403095347198E292

```