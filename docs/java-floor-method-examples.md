# Java floor()方法示例

> 原文:[https://www.geeksforgeeks.org/java-floor-method-examples/](https://www.geeksforgeeks.org/java-floor-method-examples/)

**java.lang.Math.floor()** 返回小于或等于参数且等于最接近的数学整数的双精度值。
T3【注:

*   如果参数是**整数**，那么**结果**就是**整数**。
*   如果自变量是 **NaN** 或一个**无穷大**或**正零**或**负零**，那么**结果**就是与自变量相同的**。**

> ****公共静态双楼层(双 a)**
> **a :** 待确定楼层值的参数
> **返回:**此方法返回小于或等于参数
> 且等于最接近的数学整数的双值。**

****例:**展示 **java.lang.Math.floor()** 方法的工作。**

```java
// Java program to demonstrate working
// of java.lang.Math.floor() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = 4.3;
        double b = 1.0 / 0;
        double c = 0.0;
        double d = -0.0;
        double e = -2.3;

        System.out.println(Math.floor(a));

        // Input Infinity, Output Infinity
        System.out.println(Math.floor(b));

        // Input Positive Zero, Output Positive Zero
        System.out.println(Math.floor(c));

        // Input Negative Zero, Output Negative Zero
        System.out.println(Math.floor(d));

        // Input -2.3, Output -3.0
        // Nearest Integer(-3.0) < less than (-2.3)
        System.out.println(Math.floor(e));
    }
}
```

****输出:****

```java
4.0
Infinity
0.0
-0.0
-3.0 
```