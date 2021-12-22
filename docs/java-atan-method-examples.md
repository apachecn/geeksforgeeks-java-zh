# Java atan()方法示例

> 原文:[https://www.geeksforgeeks.org/java-atan-method-examples/](https://www.geeksforgeeks.org/java-atan-method-examples/)

**java.lang.Math.atan()** 返回-pi/2 到 pi/2 之间角度的反正切。如果参数是 NaN，那么结果就是 NaN。

**注:**如果自变量为零，则结果为与自变量符号相同的零。

**语法:**

```
public static double atan(double a)
Parameter :
a : the value whose arc tangent is to be returned.
Return :
This method returns the arc tangent of the argument.
```

**示例:**展示 **java.lang.Math.atan()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.atan() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = Math.PI;

        System.out.println(Math.atan(a));

        double c = 344.0;
        double d = 0.0;
        double e = -0.0;
        double f = 1.5;

        System.out.println(Math.atan(c));

        // Input positive zero
        // Output positive zero
        System.out.println(Math.atan(d));

        // Input negative zero
        // Output negative zero
        System.out.println(Math.atan(e));

        System.out.println(Math.atan(f));
    }
}
```

**输出:**

```
1.2626272556789115
1.5678893582391513
0.0
-0.0
0.982793723247329

```