# Java cbrt()方法示例

> 原文:[https://www.geeksforgeeks.org/java-cbrt-method-examples/](https://www.geeksforgeeks.org/java-cbrt-method-examples/)

**java.lang.Math.cbrt()** 方法返回一个双精度值的立方根。
T3【注:

*   **T2 负值**的立方根是该值大小的**立方根**的**负值**。
*   如果论证是 **NaN** ，那么**的结果**就是 **NaN** 。
*   如果参数为**无穷大**，则**结果**为**无穷大**，符号**与参数相同**。
*   如果参数为**零**，则**结果**为**零**，符号**与参数相同**。

**语法:**

```
public static double cbrt(double a)
Parameter :
a : an argument
Return :
This method returns the cube root of a.
```

**示例:**展示 **java.lang.Math.cbrt()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.cbrt() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = 125.0;
        double b = 1.0 / 0;
        double c = -(1.0 / 0);
        double d = 0.0;
        double e = -0.0;

        System.out.println(Math.cbrt(a));

        // Input Positive Infinity
        // Output Positive Infinity
        System.out.println(Math.cbrt(b));

        // Input Negative Infinity
        // Output Negative Infinity
        System.out.println(Math.cbrt(c));

        // Input Positive Zero
        // Output Positive Zero
        System.out.println(Math.cbrt(d));

        // Input Negative Zero
        // Output Negative Zero
        System.out.println(Math.cbrt(e));
    }
}
```

**输出:**

```
5.0
Infinity
-Infinity
0.0
-0.0

```