# Java 中的 BigDecimal doubleValue()方法

> 原文:[https://www . geesforgeks . org/big decimal-double value-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-doublevalue-method-in-java/)

**Java . math . BigDecimal . double value()**是一个内置函数，它将 *BigDecimal* 对象转换为双精度值。该功能将*双十进制*转换为*双十进制。NEGATIVE_INFINITY* 或 *Double。POSITIVE_INFINITY* 视情况而定，或者根据传递的对象，如果其大小太大而不能表示为双精度。

**注意:**给定 *BigDecimal* 值的 Double 值的小数精度信息，即使返回值是有限的，也会丢失。

**语法:**

```java
public double doubleValue()
```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回这个 BigDecimal 对象的双精度值。

**示例:**

```java
Input : 11234
Output : 11234.0

Input : 2679.30000
Output : 2679.3

```

下面的程序说明了 byteValueExact()函数的使用:
**程序 1:**

```java
// Java program to demonstrate doubleValue() method
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigDecimal object
        BigDecimal big;

        // Creating a Double object
        Double dob;

        big = new BigDecimal("4743");

        // Assigning the converted value of bg to d
        dob = big.doubleValue();

        // Printing the corresponding double value
        System.out.println("Double value of " + big + " is " + dob);
    }
}
```

**Output:**

```java
Double value of 4743 is 4743.0

```

**程序 2:**

```java
// Java program to demonstrate doubleValue() method
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigDecimal object
        BigDecimal big;

        // Creating a Double object
        Double dob;

        big = new BigDecimal("6714592679.34008");

        // Assigning the converted value of bg to d
        dob = big.doubleValue();

        // Printing the corresponding double value
        System.out.println("Double value of " + big + " is " + dob);
    }
}
```

**Output:**

```java
Double value of 6714592679.34008 is 6.71459267934008E9

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # double value()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#doubleValue())