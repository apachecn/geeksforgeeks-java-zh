# Java 数学 tan()方法示例

> 原文:[https://www . geesforgeks . org/Java-math-tan-method-examples/](https://www.geeksforgeeks.org/java-math-tan-method-examples/)

**java.lang.Math.tan()** 返回一个角度的三角正切值。

*   如果参数是 NaN 或无穷大，则返回的结果是 NaN。
*   If the argument is zero, then the result is a zero with the same sign as the argument.

    **语法:**

    ```java
    public static double tan(double angle)
    Parameters :
    The function has one mandatory parameter angle which is in radians. 

    ```

    **返回:**
    函数返回一个角度的三角正切值。

    **例 1 :** 展示 java.lang.Math.tan()方法的工作原理。

    ```java
    // Java program to demonstrate working
    // of java.lang.Math.tan() method
    import java.lang.Math;

    class Gfg {

        // driver code
        public static void main(String args[])
        {
            double a = 30;

            // converting values to radians
            double b = Math.toRadians(a);

            System.out.println(Math.tan(b));

            a = 45;

            // converting values to radians
            b = Math.toRadians(a);

            System.out.println(Math.tan(b));

            a = 60;

            // converting values to radians
            b = Math.toRadians(a);

            System.out.println(Math.tan(b));

            a = 0;

            // converting values to radians
            b = Math.toRadians(a);

            System.out.println(Math.tan(b));
        }
    }
    ```

    输出:

    ```java
    0.5773502691896257
    0.9999999999999999
    1.7320508075688767
    0.0

    ```

    **例 2 :** 展示当参数为 n an 或无穷大时，java.lang.Math.tan()方法的工作原理。

    ```java
    // Java program to demonstrate working
    // of java.lang.Math.tan() method infinity case
    import java.lang.Math;

    public class GFG {
        public static void main(String[] args)
        {

            double positiveInfinity = 
                   Double.POSITIVE_INFINITY;
            double negativeInfinity = 
                   Double.NEGATIVE_INFINITY;
            double nan = Double.NaN;
            double result;

            // Here argument is negative infinity, 
            // output will be NaN
            result = Math.tan(negativeInfinity);
            System.out.println(result);

            // Here argument is positive infinity, 
            // output will also be NaN
            result = Math.tan(positiveInfinity);
            System.out.println(result);

            // Here argument is NaN, output will be NaN
            result = Math.tan(nan);
            System.out.println(result);
        }
    }
    ```

    输出:

    ```java
    NaN
    NaN
    NaN

    ```