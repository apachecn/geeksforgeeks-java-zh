# Java 中的大整数减法()方法，示例

> 原文:[https://www . geesforgeks . org/big integer-减法-Java-in-method-with-examples/](https://www.geeksforgeeks.org/biginteger-subtract-method-in-java-with-examples/)

java.math.BigInteger 。减法(BigInteger val)用于计算两个 BigInteger 的算术差。该方法适用于范围远大于 Java 最大数据类型 double 范围的大数值，不会影响结果的精度，但由于 BigInteger 类内部使用整数数组进行处理，因此对 big integer 对象的操作不如对原语的操作快。此方法对调用此方法的当前大整数执行操作，并将大整数作为参数传递。

**语法:**

```
public BigInteger subtract(BigInteger val)

```

**参数:**该方法接受一个参数**值**，它是要从这个大整数中减去的值。

**返回值:**这个方法返回一个保存差值(This–val)的大整数。

下面的程序用来说明 BigInteger 的减法()方法。

**例 1:**

```
// Java program to demonstrate
// subtract() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger diff;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the difference
        String input1
            = "56454210032311316797946498748";
        String input2
            = "34664864678464621214565587864";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Using subtract() method
        diff = a.subtract(b);

        // Display the result in BigInteger
        System.out.println("The difference of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + diff);
    }
}
```

**Output:**

```
The difference of
56454210032311316797946498748 
and
34664864678464621214565587864 
is
21789345353846695583380910884

```

**例 2:**

```
// Java program to demonstrate
// subtract() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger diff;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the difference
        String input1 = "012345678901234567"
                        + "8901234567890123"
                        + "4567890123456789"
                        + "0123456789012345"
                        + "6789012345678901"
                        + "2345678901234567"
                        + "8901234567890123"
                        + "4567890123456789"
                        + "0123456789012345"
                        + "6789012345678901"
                        + "2345678901234567"
                        + "8901234567890123"
                        + "4567890123456789"
                        + "0123456789012345"
                        + "6789012345678901"
                        + "2345678901234567"
                        + "8901234567890123"
                        + "4554324324362432"
                        + "7674637264783264"
                        + "7832678463726478"
                        + "3264736274673864"
                        + "7364732463546354"
                        + "6354632564532645"
                        + "6325463546536453"
                        + "6546325463546534"
                        + "6325465345326456"
                        + "4635463263453264"
                        + "654632498739473";

        String input2 = "0123456789012345"
                        + "6789012345678901"
                        + "2345678901234567"
                        + "8901234567890123"
                        + "4567890123456789"
                        + "0123456789012345"
                        + "6789012345678901"
                        + "2345678901234567"
                        + "8901234567890123"
                        + "4567890123456789"
                        + "0123456789012345"
                        + "6789012345678901"
                        + "2345678901234567"
                        + "8901234567890123"
                        + "4567890123456789"
                        + "0123456789012345"
                        + "6789012345678901"
                        + "2345873271893718"
                        + "2974897146378481"
                        + "7489127847281478"
                        + "2174871248721847"
                        + "8748327463756475"
                        + "6745781641263981"
                        + "2839721897438974"
                        + "3286574365764576"
                        + "2376914689217817"
                        + "4362473624721647"
                        + "61247612748612746";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Using subtract() method
        diff = a.subtract(b);

        // Display the result in BigInteger
        System.out.println("The difference of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + diff);

        // Using double to hold  the result
        double d = Double.parseDouble(diff.toString());

        // Display the result in double
        System.out.println("Using double, difference is "
                           + d);
    }
}
```

**Output:**

> 的差异 1234567890123456789 . 01234567901

从上面的例子可以清楚地看出，当使用 BigInteger 时，数据是完全精确的。

**参考:**[https://docs . Oracle . com/en/Java/javae/12/docs/API/Java . base/Java/math/big integer . html # subtract(Java . math . big integer)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#subtract(java.math.BigInteger))