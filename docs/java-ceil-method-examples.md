# Java ceil()方法示例

> 原文:[https://www.geeksforgeeks.org/java-ceil-method-examples/](https://www.geeksforgeeks.org/java-ceil-method-examples/)

**java.lang.Math.ceil()** 返回大于或等于参数且等于最接近的数学整数的双精度值。
T3【注:

*   如果参数是**整数**，那么**结果**就是**整数**。
*   如果自变量是 **NaN** 或一个**无穷大**或**正零**或**负零**，那么**结果**就是与自变量相同的**。**
*   **如果参数值**小于零但大于-1.0** ，则**结果**为**负零**。**

****语法:****

> ****公共静态双天花板(双 a)**
> **a :** 天花板值待确定的自变量
> **返回:**此方法返回大于或等于自变量
> 且等于最接近的数学整数的双值。**

****示例:**展示 **java.lang.Math.ceil()** 方法的工作。**

```java
// Java program to demonstrate working
// of java.lang.Math.ceil() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = 4.3;
        double b = 1.0 / 0;
        double c = 0.0;
        double d = -0.0;
        double e = -0.12;

        System.out.println(Math.ceil(a));

        // Input Infinity, Output Infinity
        System.out.println(Math.ceil(b));

        // Input Positive Zero, Output Positive Zero
        System.out.println(Math.ceil(c));

        // Input Negative Zero, Output Negative Zero
        System.out.println(Math.ceil(d));

        // Input  less than zero but greater than -1.0
        // Output Negative zero
        System.out.println(Math.ceil(e));
    }
}
```

****输出:****

```java
5.0
Infinity
0.0
-0.0
-0.0 
```