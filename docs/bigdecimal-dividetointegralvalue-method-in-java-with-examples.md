# Java 中的 BigDecimal divideToIntegralValue()方法，带示例

> 原文:[https://www . geesforgeks . org/big decimal-dividetointegralvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-dividetointegralvalue-method-in-java-with-examples/)

T2。用于计算两个大小数的商的整数部分**(这个/除数)**向下舍入。结果的优选尺度是(这个。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/)–除数。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/))。此方法对调用此方法的当前大十进制数和作为参数传递的大十进制数执行操作。

Java 中有两种 divideToIntegralValue 方法重载，如下所示:

*   **股利分红(BigDecimal 除数)**
*   **股利分红(BigDecimal divisor，MathContext mc)**

### BigDecimal 除数

**语法:**

```
public BigDecimal divideToIntegralValue(BigDecimal divisor)

```

**参数:**这个方法接受一个参数**除数**，这个大十进制数将除以这个参数。
**返回值:**这个方法返回一个 BigDecimal，保存结果的整数部分 **(this /除数)**。
**异常:**参数**除数**一定不能为 **0** 否则抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。

下面的程序用来说明大十进制的 divideToIntegralValue()方法。

```
// Java program to demonstrate
// divideToIntegralValue() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values
        String input1
            = "31452678569";
        String input2
            = "2468";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Using divideToIntegralValue() method
        res = a.divideToIntegralValue(divisor);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```
12744197

```

### BigDecimal 除数(MathContext mc)

由于精确商的整数部分不依赖于舍入模式，因此舍入模式不影响此方法返回的值。结果的优选尺度是(这个。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/)–除数。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/))。

**语法:**

```
public BigDecimal divideToIntegralValue(BigDecimal divisor,
                                        MathContext mc)

```

**参数:**该方法接受一个参数**除数**和一个参数**MC****math context**进行上下文设置。
**返回值:**该方法返回一个大十进制数，保存结果的整数部分 **(this /除数)**。
**异常:**该方法针对以下情况抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/):

*   参数**除数**不得为 **0** 。
*   如果 **mc.precision > 0** 并且结果需要超过 **mc.precision** 位数的精度。

下面的程序用来说明大十进制的 divideToIntegralValue()方法。
**例 1:**

```
// Java program to demonstrate
// divideToIntegralValue() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values
        String input1
            = "24536482";
        String input2
            = "2";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Set precision to 10
        MathContext mc
            = new MathContext(10);

        // Using divideToIntegralValue() method
        res = a.divideToIntegralValue(divisor, mc);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```
12268241

```

**示例 2:** 说明 divideToIntegralValue()方法中发生异常的程序

```
// Java program to demonstrate
// divideToIntegralValue() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values
        String input1
            = "24536482";
        String input2
            = "2";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Set precision to 5
        MathContext mc
            = new MathContext(5);

        // As the result requires
        // a precision of more than
        // mc.precision digits
        // So Exception occur
        try {

            // Using divideToIntegralValue() method
            res = a.divideToIntegralValue(divisor, mc);

            // Display the result in BigDecimal
            System.out.println(res);
        }
        catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
java.lang.ArithmeticException: Division impossible

```

**参考文献:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # divideToIntegralValue(Java . math . bigdecimal)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divideToIntegralValue(java.math.BigDecimal))