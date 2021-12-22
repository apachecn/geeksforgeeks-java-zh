# Java 数学 getindex()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-math-get index-method-example-2/](https://www.geeksforgeeks.org/java-math-getexponent-method-example-2/)

**Java . lang . math . getindex()**是一个内置的数学函数，它返回浮点表示中使用的无偏指数。

*   如果参数是 NaN 或无穷大，那么结果就是 **Float。MAX _ INDEX+1。**
*   如果参数为零或低于正常值，则结果为 **Float。最小指数-1。**

**语法:**

```
public static int getExponent(float val)
Parameter:
val - a float value
```

**返回:**
该方法返回参数的**无偏指数**。

**示例:**展示**函数的工作**

```
// Java program to demonstrate working
// of java.lang.Math.getExponent() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {

        float x = 7689.1f;
        float y = -794.99f;

        // print the unbiased exponent of them
        System.out.println(Math.getExponent(x));
        System.out.println(Math.getExponent(y));

        // print the unbiased exponent of 0
        System.out.println(Math.getExponent(0));
    }
}
```

**输出:**

```
12
9
-127

```