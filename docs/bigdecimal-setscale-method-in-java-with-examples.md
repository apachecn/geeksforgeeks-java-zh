# Java 中的 BigDecimal setScale()方法，带示例

> 原文:[https://www . geesforgeks . org/big decimal-set scale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-setscale-method-in-java-with-examples/)

T2。setScale() 用于设置 BigDecimal 的小数位数。此方法对调用此方法的当前大十进制数执行操作。

Java 中有三种 setScale()方法重载，如下所示:

*   **设置刻度(整数新刻度)**
*   **设置刻度(整数新刻度，整数模式)**
*   **setScale（int newScale， RoundingMode roundingMode）**

**注:**自 Java 9 以来，**设置刻度(int newScale，int roundingMode)** 已被**弃用。**

### 设置刻度(整数新刻度)

当保证存在指定比例的大十进制数和正确值时，此调用通常用于增加比例。如果用户知道 BigDecimal 的小数部分末尾有足够多的零，允许在不改变其值的情况下进行重新缩放，则该调用也可用于缩小比例。
**语法:**

```
public BigDecimal setScale(int newScale)

```

**参数:**该方法接受一个参数**新刻度**，用于设置该大十进制的刻度。
**返回值:**此方法返回一个大十进制数，其小数位数为指定值。
**异常:**如果指定的缩放操作需要舍入，则抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。
**注意:**由于 BigDecimal 对象是不可变的，调用此方法不会导致原始对象被修改，所以 setScale 返回一个具有适当比例的对象。返回的对象可能是新分配的，也可能不是。

下面的程序用来说明 BigDecimal 的 setScale()方法。

```
// Java program to demonstrate
// setScale() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Object of String created
        // Holds the value
        String input1
            = "31452678569.25";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);

        // Scale for BigDecimal
        int newScale = 4;

        // Using setScale() method
        res = a.setScale(newScale);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```
31452678569.2500

```

### setScale（int newScale， int roundingMode）

此方法用于计算一个大十进制数，其小数位数为指定值，其未缩放值通过将该大十进制数的未缩放值乘以或除以适当的十次方来确定，以保持其整体值。如果操作缩小了比例，那么未缩放的值必须被除(而不是相乘)。指定的舍入模式应用于除法。
**语法:**

```
public BigDecimal setScale(int newScale, int roundingMode)

```

**参数:**该方法接受两个参数**新刻度**，用于设置该大十进制的刻度，**舍入模式**用于设置结果的舍入值。
**返回值:**该方法返回一个大十进制数，其小数位数为指定值。
**异常:**如果舍入模式是不必要的，并且指定的缩放操作需要舍入，则该方法抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。如果舍入模式不代表有效的舍入模式，该方法还会抛出[IllegalArgumentException](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。

下面的程序用来说明 BigDecimal 的 setScale()方法。
**例 1:**

```
// Java program to demonstrate
// setScale() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Object of String created
        // Holds the value
        String input1
            = "31452678569.24";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);

        // Scale for BigDecimal
        int newScale = -1;
        try {

            // Using setScale() method
            res = a.setScale(newScale, 1);

            // Display the result in BigDecimal
            System.out.println(res);
        }
        catch (Exception e) {

            // Print Exception
            System.out.println(e);
        }
    }
}
```

**Output:**

```
3.145267856E+10

```

**示例 2:** 显示此方法引发的异常的程序。

```
// Java program to demonstrate
// setScale() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Object of String created
        // Holds the value
        String input1
            = "31452678569.24";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);

        // Scale for BigDecimal
        int newScale = -1;

        try {

            // Using setScale() method
            res = a.setScale(newScale, 7);

            // Display the result in BigDecimal
            System.out.println(res);
        }
        catch (Exception e) {

            // Print Exception
            System.out.println(e);
        }

        try {

            // Using setScale() method
            res = a.setScale(newScale, 10);

            // Display the result in BigDecimal
            System.out.println(res);
        }
        catch (Exception e) {

            // Print Exception
            System.out.println(e);
        }
    }
}
```

**Output:**

```
java.lang.ArithmeticException: Rounding necessary
java.lang.IllegalArgumentException: Invalid rounding mode

```

### setScale（int newScale， RoundingMode roundingMode）

此方法用于计算一个大十进制数，其小数位数为指定值，其未缩放值通过将该大十进制数的未缩放值乘以或除以适当的十次方来确定，以保持其整体值。如果操作缩小了比例，那么未缩放的值必须被除(而不是相乘)。指定的舍入模式应用于除法。
**语法:**

```
public BigDecimal setScale(int newScale, RoundingMode roundingMode)

```

**参数:**该方法接受两个参数**新标度**，用于设置该大十进制的标度和**舍入模式[类型的](https://docs.oracle.com/javase/7/docs/api/java/math/RoundingMode.html)**舍入模式，告知应用哪种舍入模式。
**返回值:**此方法返回一个大十进制数，其小数位数为指定值。
**异常:**如果舍入模式是不必要的，并且指定的缩放操作需要舍入，则该方法抛出[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)。

下面的程序用来说明 BigDecimal 的 setScale()方法。
**例 1:**

```
// Java program to demonstrate
// setScale() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Object of String created
        // Holds the value
        String input1
            = "31452678569.24";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);

        // Scale for BigDecimal
        int newScale = 1;

        try {

            // Using setScale() method
            // Using RoundingMode.CEILING
            res = a.setScale(newScale, RoundingMode.CEILING);

            // Display the result in BigDecimal
            System.out.println(res);
        }
        catch (Exception e) {

            // Print Exception
            System.out.println(e);
        }
    }
}
```

**Output:**

```
31452678569.3

```

**示例 2:** 显示此方法引发的异常的程序。

```
// Java program to demonstrate
// setScale() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Object of String created
        // Holds the value
        String input1
            = "31452678569.24";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);

        // Scale for BigDecimal
        int newScale = -1;

        try {

            // Using setScale() method
            // Using RoundingMode.UNNECESSARY
            res = a.setScale(newScale, RoundingMode.UNNECESSARY);

            // Display the result in BigDecimal
            System.out.println(res);
        }
        catch (Exception e) {

            // Print Exception
            System.out.println(e);
        }
    }
}
```

**Output:**

```
java.lang.ArithmeticException: Rounding necessary

```

**参考文献:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # setScale(int)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#setScale(int))