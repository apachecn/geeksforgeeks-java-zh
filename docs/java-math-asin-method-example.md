# Java 数学 asin()方法示例

> 原文:[https://www . geesforgeks . org/Java-math-asin-method-example/](https://www.geeksforgeeks.org/java-math-asin-method-example/)

java.lang.Math.asin()返回 **-pi/2 和 pi/2 之间角度的反正弦。**反正弦也叫正弦的逆。

*   如果参数为 NaN 或其绝对值大于 1，则结果为 NaN。
*   如果该参数为零，则结果是一个零，其符号与该参数相同。

**语法:**

```
public static double asin(double angle)
Parameter :
angle : the value whose arc sine is to be returned.

```

**返回:**
这个方法返回参数的反正弦。

**例 1 :** 展示 java.lang.Math.asin()方法的工作原理。

```
// Java program to demonstrate working
// of java.lang.Math.asin() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = Math.PI;

        // Output is NaN, because Math.PI gives 3.141 value
        // greater than 1
        System.out.println(Math.asin(a));

        // convert Math.PI to radians
        double b = Math.toRadians(a);

        System.out.println(Math.asin(b));

        double c = 1.0;
        System.out.println(Math.asin(c));

        double d = 0.0;
        System.out.println(Math.asin(d));

        double e = -1.0;
        System.out.println(Math.asin(e));

        double f = 1.5;

        // value of f does not lie in between -1 and 1
        // so output is NaN
        System.out.println(Math.asin(f));
    }
}
```

**输出:**

```
NaN
0.054858647341251204
1.5707963267948966
0.0
-1.5707963267948966
NaN

```