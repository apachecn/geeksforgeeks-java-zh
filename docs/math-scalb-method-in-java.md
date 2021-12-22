# Java 中的数学 scalb()方法

> 原文:[https://www.geeksforgeeks.org/math-scalb-method-in-java/](https://www.geeksforgeeks.org/math-scalb-method-in-java/)

1.  The **scalb(*double a, int scale* )** is an inbuilt method of Math class in Java which is used to get the value *a* x 2^*scale* . The result is accurately calculated when the exponent of the result is between Double.MIN_EXPONENT and Double.MAX_EXPONENT. It gives rise to four special results:
    *   当结果的指数大于 Double 时，它返回无穷大。MAX _。
    *   当第一个参数是 NaN 时，结果是 NaN。
    *   当第一个参数为无穷大时，结果是同一个符号的无穷大。
    *   当第一个参数为零时，它返回相同符号的零。

    **语法:**

    ```java
    public static double scalb(*double a, int scale*)
    ```

    **参数:**该方法接受两个参数，它们是:

    *   *a* :这是双数型，是要用 2 的幂来缩放的数。
    *   *刻度*:这是 2 的幂的整数型，用来刻度 *a*

    **返回值:**该方法返回 *a* x 2^ *刻度*
    **示例:**

    ```java
    Input: 
    a = 77.23
    scale = 3

    Output = 617.84

    ```

    下面的程序说明了 Java . lang . math . scalb(*double a，int scale* )方法:

    ```java
    // Java praogram to illustrate the
    // java.lang.Math.scalb(double a, int scale )
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double p = 52.12;
            int scale = 8;

            // It returns p x 2^scale
            System.out.print("Value of Math.scalb(" 
                         + p + ", " + scale + ") = ");
            System.out.println(Math.scalb(p, scale));
        }
    }
    ```

    **Output:**

    ```java
    Value of Math.scalb(52.12, 8) = 13342.72

    ```

2.  The **java.lang.Math.scalb(*float a, int scale* )** is an inbuilt method which returns *a* x 2^*scale* . The result is accurately calculated when the exponent of the result is between Float.EXPONENT and Float.MAX_EXPONENT.
    *   当结果的指数大于浮点时，它返回无穷大。MAX _。
    *   当第一个参数是 NaN 时，结果是 NaN。
    *   当第一个参数为无穷大时，结果是同一个符号的无穷大。
    *   当第一个参数为零时，它返回相同符号的零。

    **语法:**

    ```java
    public static double scalb(*float a, int scale*)
    ```

    **参数:**该方法接受两个参数:

    *   *a* :这是浮点型的，是要用 2 的幂来缩放的数字。
    *   *标度*:整数型，是指 *a* 标度中使用的 2 的幂

    **返回值:**该方法返回 *a* x 2^ *刻度*
    **示例:**

    ```java
    Input: 
    a = 32.14f
    scale = 6

    Output = 2056.96

    ```

    下面的程序说明了 Java . lang . math . scalb(*float a，int scale* )方法:
    **程序 1:**

    ```java
    // Java praogram to illustrate the
    // java.lang.Math.scalb(float a, int scale )
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            float p = 81.27f;
            int scale = 8;

            // Calculate p multiplied by 2 raised in scale
            System.out.print("Value of Math.scalb(" +
                                p + ", " + scale + ") = ");
            System.out.println(Math.scalb(p, scale));
        }
    }
    ```

    **Output:**

    ```java
    Value of Math.scalb(81.27, 8) = 20805.12

    ```