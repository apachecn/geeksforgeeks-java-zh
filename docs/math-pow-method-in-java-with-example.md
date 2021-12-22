# Java 中的数学幂()方法，示例

> 原文:[https://www . geesforgeks . org/math-pow-method-in-Java-with-example/](https://www.geeksforgeeks.org/math-pow-method-in-java-with-example/)

**T1。pow()** 用于计算一个数与其他数的幂的乘积。该函数接受两个参数，并将第一个参数的值返回给第二个参数。下面列出了一些特殊情况:

*   如果第二个参数是正或负零，那么结果将是 1.0。
*   如果第二个参数是 1.0，那么结果将与第一个参数相同。
*   如果第二个参数是 NaN，那么结果也将是 NaN。

**语法**:

```
public static double pow(double a, double b)
Parameter:
a : this parameter is the base
b : this parameter is the exponent.
Return :
This method returns ab.

```

**例 1** :展示 **java.lang.Math.pow()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.pow() method

import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = 30;
        double b = 2;
        System.out.println(Math.pow(a, b));

        a = 3;
        b = 4;
        System.out.println(Math.pow(a, b));

        a = 2;
        b = 6;
        System.out.println(Math.pow(a, b));
    }
}
```

输出:

```
900.0
81.0
64.0

```

**例 2** :展示参数为 NaN 时 **java.lang.Math.pow()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.pow() method
import java.lang.Math; // importing java.lang package

public class GFG {
    public static void main(String[] args)
    {

        double nan = Double.NaN;
        double result;

        // Here second argument is NaN,
        // output will be NaN
        result = Math.pow(2, nan);
        System.out.println(result);

        // Here second argument is zero
        result = Math.pow(1254, 0);
        System.out.println(result);

        // Here second argument is one
        result = Math.pow(5, 1);
        System.out.println(result);
    }
}
```

输出:

```
NaN
1.0
5.0

```