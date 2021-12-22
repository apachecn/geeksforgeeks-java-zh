# Java 中的大整数乘()方法，示例

> 原文:[https://www . geeksforgeeks . org/big integer-Java 中的乘法-带示例/](https://www.geeksforgeeks.org/biginteger-multiply-method-in-java-with-examples/)

**T1 大整数。乘法(BigInteger val)** 用于计算两个 BigInteger 的乘法。由于 [BigInteger 类](https://www.geeksforgeeks.org/biginteger-class-in-java/)内部使用整数数组进行处理，对 BigInteger 对象的操作不如对原语的操作快。

**语法:**

```java
public BigInteger multiply(BigInteger val)

```

**参数:**该方法接受一个参数**值**，它是要乘以这个大整数的值。

**返回值:**这个方法返回一个保存乘法的大整数(this * val)。

**下面的程序用来说明 BigInteger 的乘()方法。**

**例 1:**

```java
// Java program to demonstrate
// multiply() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // BigInteger object to store result
        BigInteger mult;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the multiplication
        String input1 = "012345678901234567"
                        + "654632498739473";

        String input2 = "0123456789012345"
                        + "61247612748612746";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Using multiply() method
        mult = a.multiply(b);

        // Display the result in BigInteger
        System.out.println("The multiplication of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + mult);
    }
}
```

**输出:**

> 12345678901234567654632498739473
> 和
> 12345678901234561247612746
> 的乘积是
> 152415775323828 . 23456256256

**例 2:**

```java
// Java program to demonstrate
// multiply() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger mult;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the multiplication
        String input1 = "012345678901234567"
                        + "8901234567890123"
                        + "4567890123456789"
                        + "0123456789012345"
                        + "6789012345678901"
                        + "654632498739473";

        String input2 = "0123456789012345"
                        + "6789012345678901"
                        + "2345678901234567"
                        + "8901234567890123"
                        + "4567890123456789"
                        + "61247612748612746";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Using multiply() method
        mult = a.multiply(b);

        // Display the result in BigInteger
        System.out.println("The multiplication of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + mult + "\n");

        // Using double to hold  the result
        double d = Double.parseDouble(mult.toString());

        // Display the result in double
        System.out.println("Using double, multiplication is "
                           + d);
    }
}
```

**输出:**

> 12345678901234567890123456789012345678901234567890123456789012356790123456789016543249873
> 和
> 的乘法运算 1234567895 . 12345789012
> 
> 使用双精度，乘法是 1.5241578753238838E190

从上面的例子可以清楚地看出，当使用 BigInteger 时，数据是完全精确的。

**参考:**[https://docs . Oracle . com/en/Java/javae/12/docs/API/Java . base/Java/math/big integer . html # multiple(Java . math . big integer)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#multiply(java.math.BigInteger))