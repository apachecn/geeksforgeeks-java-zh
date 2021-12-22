# Java 中的 BigDecimal 余数()方法，示例

> 原文:[https://www . geesforgeks . org/big decimal-Java 中的余数方法-带示例/](https://www.geeksforgeeks.org/bigdecimal-remainder-method-in-java-with-examples/)

T2。余数(BigDecimal 除数)用于计算两个 BigDecimals 的余数。余数由此给出。[减去](https://www.geeksforgeeks.org/bigdecimal-subtract-method-in-java-with-examples/)(除数)。[乘(除数)](https://www.geeksforgeeks.org/bigdecimal-multiply-method-in-java/))。此方法对调用此方法的当前大十进制数和作为参数传递的大十进制数执行操作。

**注意:**这不是模运算(结果可以是负数)。

Java 中有两种余数方法重载，如下所示:

*   **[remainder (large decimal divisor)**
*   **remainder (big decimal divisor, MathContext MC)**

### 余数(十进制除数)

**语法:**

```
public BigDecimal remainder(BigDecimal divisor)

```

**参数:**这个方法接受一个参数**除数**，这个大十进制数要除以这个参数才能得到余数。

**返回值:**这个方法返回一个大十进制数，保存结果**(这个%除数)**。

**异常:**参数**除数**一定不能为 **0** 否则抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。

下面的程序用来说明 BigDecimal 的余数()方法。

```
// Java program to demonstrate
// remainder() method of BigDecimal

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

        // Using remainder() method
        res = a.remainder(divisor);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**输出:**

```
373

```

### 余数(BigDecimal 除数，MathContext mc)

该方法用于计算值为**(本%除数)**的两个 BigDecimals 的余数，根据上下文设置进行四舍五入。MathContext 设置影响用于计算余数的隐式除法。因此，余数可能包含超过 **mc.getPrecision()** 位的数字。

**语法:**

```
public BigDecimal remainder(BigDecimal divisor, MathContext mc)

```

**参数:**这个方法接受一个参数**除数**，这个大十进制将被这个除数除，以及一个类型为 **MathContext** 的参数 **mc** 用于上下文设置。

**返回值:**这个方法返回一个 BigDecimal，保存结果**(这个%除数)**。

**异常:**方法抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)以下情况:

*   Parameter **divisor** must not be **0** .
*   If **MC. Precision > 0** and the required precision of the result exceeds **MC. Precision** digits.

下面的程序是用来说明 BigDecimal 的余数()方法的。

```
// Java program to demonstrate
// remainder() method of BigDecimal

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
            = "264";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Set precision to 5
        MathContext mc
            = new MathContext(5);

        // Using remainder() method
        res = a.remainder(divisor, mc);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**输出:**

```
58

```

**参考文献:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html #余数(Java . math . bigdecimal)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#remainder(java.math.BigDecimal))