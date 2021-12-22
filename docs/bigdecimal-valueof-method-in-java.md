# Java 中的 BigDecimal valueOf()方法

> 原文:[https://www . geesforgeks . org/big decimal-value of-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-valueof-method-in-java/)

1.  The **java.math.BigDecimal.valueOf(long val)** is an inbuilt method in java that translates a long value into a BigDecimal value with a scale of zero. It allows us, the reuse of frequently used BigDecimal values and hence this “static factory method” is provided in preference to a (long) constructor.

    **语法:**

    ```
    public static BigDecimal valueOf(long val)
    ```

    **参数:**该方法接受 Long 数据类型的单个参数*值*，并引用需要转换为 BigDecimal 值的值。

    **返回值:**该方法返回一个大十进制值龙*值*。

    下面的程序举例说明了 Java . math . bigdecimal . value of(long val)方法的工作原理:

    ```
    // Program to demonstrate valueOf(long) method of BigDecimal 

    import java.math.*;

    public class gfg {

        public static void main(String[] args)
        {

            // Creating a Long Object
            Long ln = new Long("745812345678");

            // Assigning the bigdecimal value of ln to b
            BigDecimal b = BigDecimal.valueOf(ln);

            // Displaying BigDecimal value
            System.out.println("The Converted BigDecimal value is: "+b);
        }
    }
    ```

    **Output:**

    ```
    The Converted BigDecimal value is: 745812345678

    ```

2.  The **java.math.BigDecimal.valueOf(double val)** is an inbuilt method in java that translates a double into a BigDecimal, using the double’s canonical string representation provided by the Double.toString(double) method.

    **语法:**

    ```
    public static BigDecimal valueOf(double val)

    ```

    **参数:**该方法接受双数据类型的单个参数*值*，并引用需要转换为大十进制值的值。

    **返回值:**该方法返回一个大十进制值，该值等于或近似等于双*值*。

    下面的程序说明了 Java . math . bigdecimal . value of(double val)方法的工作:
    **程序 1:**

    ```
    // Program to demonstrate valueOf(double) method of BigDecimal 

    import java.math.*;

    public class gfg {

        public static void main(String[] args)
        {

            // Creating a Double Object
            Double d = new Double("785.254");

            /// Assigning the bigdecimal value of ln to b
            BigDecimal b = BigDecimal.valueOf(d);

            // Displaying BigDecimal value
            System.out.println("The Converted BigDecimal value is: " + b);
        }
    }
    ```

    **Output:**

    ```
    The Converted BigDecimal value is: 785.254

    ```