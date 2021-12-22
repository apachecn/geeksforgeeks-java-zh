# Java 中的 BigDecimal divide()方法，示例

> 原文:[https://www . geesforgeks . org/big decimal-divide-in-Java-method-with-examples/](https://www.geeksforgeeks.org/bigdecimal-divide-method-in-java-with-examples/)

T2。除法(大小数除数)用于计算两个大小数的**商**。**商**由**(这个/除数)**给出。此方法对调用此方法的当前大十进制数和作为参数传递的大十进制数执行操作。

Java 中有五个 divide 方法重载，如下所示:

*   **除(大十进制除数)**
*   **除数(十进制除数，数学上下文 mc)**
*   **除(大十进制除数，舍入模式舍入模式)**
*   **除(大十进制除数，整数比例，舍入模式舍入模式)**
*   **除(大十进制除数，整数模)**

**注:**方法**除(大十进制除数，整数模)**因 **Java 9** 而被弃用。

### 除法(十进制除数)

**商**由**(这个/除数)**给出，其优选标度是(这个。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/)–除数。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/))。
**语法:**

```java
public BigDecimal divide(BigDecimal divisor)

```

**参数:**这个方法接受一个参数**除数**，这个大十进制要除以这个参数才能得到商。
**返回值:**这个方法返回一个 BigDecimal，保存结果 **(this /除数)**。
**异常:**如果参数**除数**为 **0** 或者精确商没有终止十进制展开，则抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。

下面的程序用来说明 BigDecimal 的 divide()方法。

```java
// Java program to demonstrate
// divide() method of BigDecimal

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
            = "204800000";
        String input2
            = "256";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Using divide() method
        res = a.divide(divisor);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java
800000

```

**参考:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # divide(Java . math . bigdecimal)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal))

### divide(十进制分隔符，MathContext mc)

该方法用于计算值为 **(this /除数)**的两个大小数的商，根据上下文设置取整。
**语法:**

```java
public BigDecimal divide(BigDecimal divisor,
                         MathContext mc)

```

**参数:**该方法接受两个参数:

*   **除数**除以这个大十进制数
*   上下文设置的**数学上下文**类型的 **mc** 。

**返回值:**该方法返回一个大十进制数，保存结果 **(this /除数)**，并根据需要进行舍入。

**异常:**如果结果不精确，但舍入模式为不必要或 mc.precision == 0，并且商具有非终止十进制展开，则该方法抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。

下面的程序用来说明 BigDecimal 的 divide()方法。

```java
// Java program to demonstrate
// divide() method of BigDecimal

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

        // Using divide() method
        res = a.divide(divisor, mc);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java
92941

```

**参考:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # divide(Java . math . bigdecimal，java.math.MathContext)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal, java.math.MathContext))

### 除法(大十进制除数，舍入模式舍入模式)

**商**由**(这个/除数)**给出，其优选标度是这个。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/)。如果需要舍入来生成给定比例的结果，则应用特定的舍入模式。
**语法:**

```java
public BigDecimal divide(BigDecimal divisor,
                         RoundingMode roundingMode)

```

**参数:**该方法接受两个参数:

*   **除数**除以这个大十进制数
*   **舍入模式[舍入模式](https://docs.oracle.com/javase/7/docs/api/java/math/RoundingMode.html)类型的舍入模式**，告知应用哪种舍入模式。

**返回值:**这个方法返回一个大十进制数，保存结果**(这个/除数)**。
**异常:**如果 roundingMode 不必要且 this.scale()不足以准确表示除法结果或**除数**为 0，则该方法抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。

下面的程序用来说明 BigDecimal 的 divide()方法。

```java
// Java program to demonstrate
// divide() method of BigDecimal

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
            = "2453648454542";
        String input2
            = "264";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Using divide() method
        // Using RoundingMode.CEILING
        res = a.divide(divisor, RoundingMode.CEILING);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java
9294122934

```

**参考:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # divide(Java . math . bigdecimal，java.math.RoundingMode)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal, java.math.RoundingMode))

### 除法(十进制除数，整数比例，舍入模式舍入模式)

**商**由**(这个/除数)**给出，其优选标度是指定的。如果需要舍入来生成具有指定比例的结果，则应用指定的舍入模式。
**语法:**

```java
public BigDecimal divide(BigDecimal divisor, 
                         int scale, 
                         RoundingMode roundingMode)

```

**参数:**该方法接受三个参数:

*   **除数**除以这个大十进制数
*   **舍入模式[舍入模式](https://docs.oracle.com/javase/7/docs/api/java/math/RoundingMode.html)类型的舍入模式**,告知应用哪种舍入模式
*   **刻度**设置商的刻度。

**返回值:**这个方法返回一个大十进制数，保存结果**(这个/除数)**。
**异常:**如果舍入模式不必要且指定的小数位数不足以准确表示除法结果或**除数**为 0，则该方法抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。

下面的程序用来说明 BigDecimal 的 divide()方法。

```java
// Java program to demonstrate
// divide() method of BigDecimal

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
            = "2453648454542";
        String input2
            = "264";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Using scale = 4
        int scale = 4;

        // Using divide() method
        // Using RoundingMode.CEILING
        res = a.divide(divisor, scale,
                       RoundingMode.CEILING);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java
9294122933.8713

```

**参考:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # divide(Java . math . bigdecimal，int，java.math.RoundingMode)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal, int, java.math.RoundingMode))