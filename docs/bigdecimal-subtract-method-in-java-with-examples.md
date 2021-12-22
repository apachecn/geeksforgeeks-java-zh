# Java 中的 BigDecimal 减法()方法，示例

> 原文:[https://www . geesforgeks . org/big decimal-带示例的 java 减法方法/](https://www.geeksforgeeks.org/bigdecimal-subtract-method-in-java-with-examples/)

T2。减法(大十进制值)用于计算两个大十进制的算术差。这种方法用于在不影响结果精度的情况下找出大数的算术差。此方法对调用此方法的当前大十进制数执行操作，并将大十进制数作为参数传递。

java 中有两个**减法**方法的重载，如下所示:

*   **减去(大十进制值)**
*   **差集(十进制选择，数学上下文 mc)**

### 减法(十进制值)

**语法:**

```java
public BigDecimal subtract(BigDecimal val)

```

**参数:**该方法接受参数**值**，该值是要从该大小数中减去的值。

**返回值:**此方法返回一个大十进制数，它保存差值(This–val)，其小数位数为 max(this。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/)，瓦尔。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/))。

下面的程序是用来说明 BigDecimal 的减法()方法的。

```java
// Java program to demonstrate
// subtract() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store result
        BigDecimal diff;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the difference
        String input1
            = "545456468445645468464645";
        String input2
            = "425645648446468486486452";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal b
            = new BigDecimal(input2);

        // Using subtract() method
        diff = a.subtract(b);

        // Display the result in BigDecimal
        System.out.println("The difference of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + diff + "\n");
    }
}
```

**输出:**

> 545456464684456454684645
> 和
> 425645648446468486486452
> 的区别是
> 11981081999176981978193

### 差集(十进制选择，MathContext mc)

**语法:**

```java
public BigDecimal subtract(BigDecimal val, MathContext mc)

```

**参数:**该方法接受两个参数，一个是**值**，这是要从该大十进制中减去的值，另一个是 **mc** 类型的数学上下文。

**返回值:**该方法返回一个保存差值(This–val)的 BigDecimal，根据上下文设置进行舍入。

下面的程序是用来说明 BigDecimal 的减法()方法的。

```java
// Java program to demonstrate
// subtract() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store result
        BigDecimal diff;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the difference
        String input1
            = "468445645468464645";
        String input2
            = "4256456484464684864864";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal b
            = new BigDecimal(input2);

        // Set precision to 10
        MathContext mc
            = new MathContext(10);
        // Using subtract() method
        diff = a.subtract(b, mc);

        // Display the result in BigDecimal
        System.out.println("The difference of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + diff + "\n");
    }
}
```

**输出:**

> 468445645468464645
> 和
> 4256456484464684864864
> 的区别是
> -4.255988039E+21

**参考文献:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html #减法(java.math.BigDecimal)](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#subtract(java.math.BigDecimal))