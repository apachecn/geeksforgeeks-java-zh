# Java 中的 BigDecimal 求反()函数

> 原文:[https://www . geesforgeks . org/big decimal-否定-java 中的函数/](https://www.geeksforgeeks.org/bigdecimal-negate-function-in-java/)

1.  The **java.math.BigDecimal.negate()** method returns a BigDecimal whose value is the negated value of the BigDecimal with which it is used.

    **语法:**

    ```
    public BigDecimal negate()
    ```

    **参数:**该方法不取任何参数。

    **返回值:**该方法返回 BigDecimal 对象的负值，其小数位数为 this.scale()。

    下面的程序将举例说明 Java . math . bigdecimal . invoke()函数的使用:
    **程序 1 :**

    ```
    // Java program to demonstrate negate() method
    import java.math.*;

    public class GFG {

       public static void main(String[] args) {

          // Create a BigDecimal object
          BigDecimal num;

          // Assign value to num
          num = new BigDecimal("4743");

          System.out.println( "Negated value is " + num.negate() );
       }
    }
    ```

    **Output:**

    ```
    Negated value is -4743

    ```

    **程序 2:**

    ```
    // Java program to demonstrate negate() method
    import java.math.*;

    public class GFG {

       public static void main(String[] args) {

          // Create a BigDecimal object
          BigDecimal num;

          // Assign value to num
          num = new BigDecimal("-9674283517.97");

          System.out.println( "Negated value is " + num.negate() );
       }
    }
    ```

    **Output:**

    ```
    Negated value is 9674283517.97

    ```

2.  The **java.math.BigDecimal.negate(MathContext mc)** method returns a BigDecimal whose value is the negated value of it, i.e. obtained by rounding off according to the precision settings specified by the object of *MathContext* class.

    **语法:**

    ```
    public BigDecimal negate(MathContext mc)
    ```

    **参数:**该方法只接受 MathContext 类对象的一个参数 *mc* ，该参数指定舍入大小数的精度设置。

    **返回值:**该方法返回对象的求反值，该值根据精度设置进行舍入。

    **异常:**如果得到的结果不准确，但舍入模式不必要，该方法可能会抛出*算术异常*。

    下面的程序将举例说明 Java . math . bigdecimal . negation(MathContext MC)方法的使用:
    **程序 1**

    ```
    // Java program to demonstrate negate(MathContext mc) method
    import java.math.*;

    public class GFG {

        public static void main(String[] args)
        {

            // create 2 BigDecimal objects
            BigDecimal num, negv;

            MathContext mc = new MathContext(4); // 4 precision

            // assign value to num
            num = new BigDecimal("78.6714");

            // assign negate value of num to negv using mc
            negv = num.negate(mc);
            System.out.println("Negated value, rounded to 4"+
            " precision " + negv);
        }
    }
    ```

    **Output:**

    ```
    Negated value, rounded to 4 precision -78.67

    ```

    **程序 2**

    ```
    // Java program to demonstrate negate(MathContext mc) method
    import java.math.*;

    public class GFG {

        public static void main(String[] args)
        {

            // create 2 BigDecimal objects
            BigDecimal num, negv;

            MathContext mc = new MathContext(12); // 12 precision

            // assign value to num
            num = new BigDecimal("-178901456.68431");

            // assign negate value of num to negv using mc
            negv = num.negate(mc);
            System.out.println("Negated value, rounded to 12 "+
            "precision " + negv);
        }
    }
    ```

    **Output:**

    ```
    Negated value, rounded to 12 precision 178901456.684

    ```

    **参考:**
    [https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # negative()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#negate())