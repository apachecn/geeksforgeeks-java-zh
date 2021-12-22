# Java 数学 getindex()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-math-get index-method-example/](https://www.geeksforgeeks.org/java-math-getexponent-method-example/)

**Java . lang . math . getindex()**返回双精度或浮点表示中使用的无偏指数。
T3【注:

*   如果参数是双或浮点类型的 **NaN** 或**无穷大**，则**结果**为( **Double。MAX _ index+1**)或( **Float。MAX _ INDEX+1**)。
*   如果参数是双精度或浮点型的**零**或**次常规**，则**结果**为(**双精度。最小指数-1** 或(**浮动。最小指数-1** )。

**语法:**

```java
public static int getExponent(DataType a)
Parameter :
a : an argument of double or float type
Return :
This method returns the unbiased exponent of the argument.
```

```java
// Java program to demonstrate working
// of java.lang.Math.getExponent() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = 345.65;
        double b = 1.0 / 0;
        double c = 0;

        // Input double value
        // Output unbiased exponent of it
        System.out.println(Math.getExponent(a));

        // Input Infinity
        // Output (Double.MAX_EXPONENT + 1)
        System.out.println(Math.getExponent(b));

        // Input Zero
        // Output (Double.MIN_EXPONENT - 1)
        System.out.println(Math.getExponent(c));

        float d = 237.2f;
        float e = 1.0f / 0;
        float f = 0f;

        // Input float value
        // Output unbiased exponent of it
        System.out.println(Math.getExponent(d));

        // Input Infinity
        // Output (Float.MAX_EXPONENT + 1)
        System.out.println(Math.getExponent(e));

        // Input Zero
        // Output (Float.MIN_EXPONENT - 1)
        System.out.println(Math.getExponent(f));
    }
}
```

**输出:**

```java
8
1024
-1023
7
128
-127

```