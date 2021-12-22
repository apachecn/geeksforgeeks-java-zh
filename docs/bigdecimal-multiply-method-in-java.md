# Java 中的 BigDecimal 乘()方法

> 原文:[https://www . geesforgeks . org/big decimal-乘法-in-java/](https://www.geeksforgeeks.org/bigdecimal-multiply-method-in-java/)

1.  The **java.math.BigDecimal.multiply(*BigDecimal multiplicand*)** is an inbuilt method in java that returns a BigDecimal whose value is (this × multiplicand), and whose scale is (this.scale() + multiplicand.scale()).

    **语法:**

    ```java
    public BigDecimal multiply(*BigDecimal multiplicand*)

    ```

    **参数:**该方法接受一个大十进制类型的单参数*被乘数*，指的是要乘以这个大十进制的值。

    **返回值:**这个方法返回一个大十进制数，它的值*这个*被乘数*。

    下面的程序说明了上述方法的工作:
    **程序 1:**

    ```java
    // Java program to demonstrate the
    // multiply() method

    import java.math.*;

    public class gfg {

        public static void main(String[] args)
        {

            // Assign two BigDecimal objects
            BigDecimal b1 = new BigDecimal("54.2");
            BigDecimal b2 = new BigDecimal("14.20");

            // Multiply b1 with b2 and assign result to b3
            BigDecimal b3 = b1.multiply(b2);

            // Print b3 value
            System.out.println("Multiplication is " + b3);
        }
    }
    ```

    **Output:**

    ```java
    Multiplication is 769.640

    ```

    **程序 2:**

    ```java
    // Java program to demonstrate the
    // multiply() method

    import java.math.*;

    public class Gfg {

        public static void main(String[] args)
        {

            // Assign two BigDecimal objects
            BigDecimal b1 = new BigDecimal("-54.2");
            BigDecimal b2 = new BigDecimal("14.20");

            // Multiply b1 with b2 and assign result to b3
            BigDecimal b3 = b1.multiply(b2);

            // Print b3 value
            System.out.println("Multiplication is " + b3);
        }
    }
    ```

    **Output:**

    ```java
    Multiplication is -769.640

    ```

2.  The **java.math.BigDecimal.multiply(*BigDecimal multiplicand, MathContext mc*)** is an inbuilt method in Java that returns a BigDecimal whose value is (this × multiplicand), with rounding according to the context settings.

    **语法:**

    ```java
    public BigDecimal multiply(*BigDecimal multiplicand, MathContext mc*)

    ```

    **参数:**该方法接受两个参数:

    *   *被乘数*–这是 BigDecimal 类型，指的是要乘以这个 BigDecimal 的值。
    *   *MC*–这是指舍入的上下文，即值要舍入到小数点后多少位。

    **返回值:**这个方法返回一个 BigDecimal，它的值是这个*被乘数，根据需要四舍五入。

    下面的程序演示了这种方法:

    **程序 1:**

    ```java
    // Java program to demonstrate the
    // multiply() method
    import java.math.*;

    public class Gfg {

        public static void main(String[] args)
        {

            // 4 precision
            MathContext m = new MathContext(4); 

            // Assign value to BigDecimal objects
            BigDecimal b1 = new BigDecimal("5.99");
            BigDecimal b2 = new BigDecimal("4.6");

            // Multiply b1 with b2 using m
            BigDecimal b3 = b1.multiply(b2, m);

            // Print b3 value
            System.out.println("Multiplication is " + b3);
        }
    }
    ```

    **Output:**

    ```java
    Multiplication is 27.55

    ```

    **程序 2:**

    ```java
    // Java program to demonstrate the
    // multiply() method
    import java.math.*;

    public class Gfg {

        public static void main(String[] args)
        {

            // 4 precision
            MathContext m = new MathContext(4); 

            // Assign value to BigDecimal objects
            BigDecimal b1 = new BigDecimal("-5.99");
            BigDecimal b2 = new BigDecimal("4.6");

            // Multiply b1 with b2 using m
            BigDecimal b3 = b1.multiply(b2, m);

            // Print b3 value
            System.out.println("Multiplication is " + b3);
        }
    }
    ```

    **Output:**

    ```java
    Multiplication is -27.55

    ```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html #乘法(java.math.BigDecimal)](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#multiply(java.math.BigDecimal))