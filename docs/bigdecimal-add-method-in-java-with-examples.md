# Java 中的 BigDecimal add()方法，带示例

> 原文:[https://www . geesforgeks . org/big decimal-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-add-method-in-java-with-examples/)

T2。add(BigDecimal val) 用于计算两个 BigDecimal 的算术和。这种方法用于寻找比 Java 的最大数据类型 double 的范围大得多的大量范围的算术加法，而不损害结果的精度。此方法对调用此方法的当前大十进制数和作为参数传递的大十进制数执行操作。

Java 中有两种 add 方法重载，如下所示:

*   **add(BigDecimal val)**
*   **add(BigDecimal val，MathContext mc)**

### add(BigDecimal val)

**语法:**

```java
public BigDecimal add(BigDecimal val)

```

**参数:**该方法接受一个参数**值**，该值是要添加到该大十进制中的值。

**返回值:**这个方法返回一个 BigDecimal，它保存 sum (this + val)，其小数位数是 max(this。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/)，瓦尔。[刻度()](https://www.geeksforgeeks.org/bigdecimal-scale-method-in-java/))。

下面的程序是用来说明 BigDecimal 的 add()方法的。

```java
// Java program to demonstrate
// add() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal sum;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the sum
        String input1
            = "545456468445645468464645";
        String input2
            = "4256456484464684864864";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal b
            = new BigDecimal(input2);

        // Using add() method
        sum = a.add(b);

        // Display the result in BigDecimal
        System.out.println("The sum of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + sum + "\n");
    }
}
```

**输出:**

> 545456468445645468464645
> 和
> 4256456484464684864864
> 之和为
> 549712924930110153329509

### 添加(十进制选择，MathContext mc)

**语法:**

```java
public BigDecimal add(BigDecimal val, MathContext mc)

```

**参数:**该方法接受两个参数，一个是**值**，该值是要添加到该大十进制中的值，另一个是类型为 MathContext 的 **mc** 。

**返回值:**这个方法返回一个 BigDecimal，保存 sum (this + val)，根据上下文设置进行舍入。如果任一数字为零，并且精度设置不为零，则另一个数字(如有必要，四舍五入)将用作结果。

下面的程序是用来说明 BigDecimal 的 add()方法的。

```java
// Java program to demonstrate
// add() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal sum;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the sum
        String input1
            = "9854228445645468464645";
        String input2
            = "4252145764464684864864";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal b
            = new BigDecimal(input2);

        // Set precision to 10
        MathContext mc
            = new MathContext(10);
        // Using add() method
        sum = a.add(b, mc);

        // Display the result in BigDecimal
        System.out.println("The sum of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + sum + "\n");
    }
}
```

**输出:**

> 98542284456454684645
> 和
> 4252145764464684864864
> 之和为
> 1.410637421E+22

**参考文献:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # add(Java . math . bigdecimal)](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#add(java.math.BigDecimal))