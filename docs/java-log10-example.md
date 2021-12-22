# Java log10()带示例

> 原文:[https://www.geeksforgeeks.org/java-log10-example/](https://www.geeksforgeeks.org/java-log10-example/)

**java.lang.Math.log10()** 是 Java Math Library 方法之一，用于返回给定双精度值的基数 10
对数值作为参数。有各种情况:

*   如果参数是**正双精度值**，Math.log10()方法将返回给定
    值的**对数。**
*   如果参数为 **NaN 或小于零**，Math.log10()方法将返回 **NaN** 。
*   如果参数为**正无穷大**，则 Math.log10()方法将返回结果为**正无穷大**。
*   If the argument is **positive or negative zero**, Math.log10() method will return the result as **Negative
    Infinity**.

    **语法:**

    ```
    public static double log10(double a)
    ```

    **参数:**

    ```
    a : User input
    ```

    **返回:**

    ```
    This method returns the base 10 logarithm of a.
    ```

    **示例:**展示 **java.lang.Math.log10()** 方法的工作。

    ```
    // Java program to demonstrate working
    // of java.lang.Math.log10() method
    import java.lang.Math;

    class Gfg {

        // driver code
        public static void main(String args[])
        {

            double a = 1000;
            double b = 145.256;
            double c = -6.04;
            double d = 1.0 / 0;
            double e = 0;

            // A power of 10 as input
            System.out.println(Math.log10(a));

            // positive double value as argument,
            // output double value
            System.out.println(Math.log10(b));

            // negative integer as argument,
            // output NAN
            System.out.println(Math.log10(c));

            // positive infinity as argument,
            // output Infinity
            System.out.println(Math.log10(d));

            // positive zero as argument,
            // output -Infinity
            System.out.println(Math.log10(e));
        }
    }
    ```

    **Output:**

    ```
    3.0
    2.1621340805671756
    NaN
    Infinity
    -Infinity

    ```