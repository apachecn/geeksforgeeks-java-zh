# Java 中的 BigDecimal abs()方法

> 原文:[https://www . geesforgeks . org/big decimal-ABS-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-abs-method-in-java/)

1.  The **java.math.BigDecimal.abs()** is used to return a BigDecimal whose value is the absolute value of the BigDecimal and whose scale is this.scale().

    **语法:**

    ```java
    public BigDecimal abs()
    ```

    **参数:**该方法不接受任何参数。

    **返回值:**返回一个 BigDecimal，其值是这个 BigDecimal 小数位数的绝对值是 this.scale()。

    下面的程序将说明 java.math.BigDecimal.abs()方法的使用:
    **程序 1**

    ```java
    // Java program to demonstrate abs() method
    import java.io.*;
    import java.math.*;

    public class GFG {

        public static void main(String[] args)
        {

            // Creating a BigDecimal object
            BigDecimal num;

            // Assigning value to num
            num = new BigDecimal("-51");

            // Displaying the result
            System.out.println("Absolute value is " + num.abs());
        }
    }
    ```

    **Output:**

    ```java
    Absolute value is 51

    ```

    **程序 2**

    ```java
    // Java program to demonstrate abs() method
    import java.io.*;
    import java.math.*;

    public class GFG {

        public static void main(String[] args)
        {

            // creating a BigDecimal object
            BigDecimal num;

            // assign value to num
            num = new BigDecimal("-63.93471");

            System.out.println("Absolute value is " + num.abs());
        }
    }
    ```

    **Output:**

    ```java
    Absolute value is 63.93471

    ```

2.  The **java.math.BigDecimal.abs(MathContext mc)** returns a BigDecimal whose value is the absolute value of the BigDecimal obtained by rounding it off according to the precision settings specified by *mc*, an object of *MathContext* class.

    **语法:**

    ```java
    public BigDecimal abs(MathContext mc)
    ```

    **参数:**该函数只接受 MathContext 类对象的一个参数 *mc* ，该参数指定了用于舍入大小数的精度设置。

    **返回值:**返回一个大十进制数，其值是根据对象 *mc* 指定的精度设置取整得到的该大十进制数的绝对值。

    **异常:**如果结果不精确但舍入模式不必要，则该方法抛出*算术异常*。

    下面的程序用指定的数学上下文说明了 java.math.BigDecimal.abs()方法的使用:
    **程序 1**

    ```java
    import java.io.*;
    import java.math.*;

    public class GFG {

        public static void main(String[] args)
        {

            // Create 2 BigDecimal objects
            BigDecimal num, absv;

            MathContext mc = new MathContext(2);

            // Assign value to num
            num = new BigDecimal("51.93471");

            // Assign absolute value of num to absv rounded 
            // to 2 precision using mc
            absv = num.abs(mc);

            System.out.println("Absolute value, rounded to 2 precision is "
            + absv);
        }
    }
    ```

    **Output:**

    ```java
    Absolute value, rounded to 2 precision is 52

    ```

    **程序 2**

    ```java
    import java.io.*;
    import java.math.*;

    public class GFG {

        public static void main(String[] args)
        {

            // Create 2 BigDecimal objects
            BigDecimal num, absv;

            MathContext mc = new MathContext(15);

            // Assign value to num
            num = new BigDecimal("143567812363.93471");

            // Assign absolute value of num to absv rounded 
            // to 15 precision using mc
            absv = num.abs(mc);

            System.out.println("Absolute value, rounded to 15 precision is " 
            + absv);
        }
    }
    ```

    **Output:**

    ```java
    Absolute value, rounded to 15 precision is 143567812363.935

    ```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # ABS()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#abs())