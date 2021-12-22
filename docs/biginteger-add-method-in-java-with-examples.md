# Java 中 BigInteger add()方法，带示例

> 原文:[https://www . geesforgeks . org/big integer-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/biginteger-add-method-in-java-with-examples/)

T2**大整数。add(BigInteger val)** 用于计算两个 BigInteger 的算术和。这种方法用于寻找比 java 的最大数据类型 double 的范围大得多的大量范围的算术加法，而不损害结果的精度。此方法对调用此方法的当前大整数执行操作，并将大整数作为参数传递。

**语法:**

```
public BigInteger add(BigInteger val)

```

**参数:**该方法接受一个参数**值**，该值是要添加到该大整数中的值。

**返回值:**这个方法返回一个保存和(this + val)的 BigInteger。

下面的程序用来说明 BigInteger 的 add()方法。

**例 1:**

```
// Java program to demonstrate
// add() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger sum;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the sum
        String input1
            = "5454564684456454684646454545";
        String input2
            = "4256456484464684864864864864";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Using add() method
        sum = a.add(b);

        // Display the result in BigInteger
        System.out.println("The sum of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + sum + "\n");
    }
}
```

**输出:**

> 545456464684456468464645454545
> 和
> 425645646484464684864864
> 之和为
> 9711021168921139549511313194

从上面的例子可以看出，即使在增加了大量的长度之后，数据仍然是完全精确的。

**例 2:**

```
// Java program to demonstrate
// add() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger sum;

        // double variable
        // To store result as double
        double d;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String
        // Holds the values to sum

        // The number's length is of 400 digits
        // Which is out of range of double
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

        // convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Using add() method
        sum = a.add(b);

        // Display the result in BigInteger
        System.out.println("The sum of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + sum);

        // Using double to hold  the result
        d = Double.parseDouble(sum.toString());

        // Display the result in double
        System.out.println("Using double, Sum is "
                           + d);
    }
}
```

**输出:**

> 之和 1234567890123456789 . 01234567901

从上面的输出可以清楚地看出，对较大的整数使用 double 不是一个好的选择。
**参考:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/big integer . html # add(Java . math . big integer)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#add(java.math.BigInteger))