# Java 中的大十进制 toString()方法，带示例

> 原文:[https://www . geesforgeks . org/big decimal-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-tostring-method-in-java-with-examples/)

T2**大十进制。toString()** 方法用于表示当前的 BigDecimal，通过该方法将该方法调用为 String 形式，如果需要指数，则使用科学表示法。它是通过以下步骤完成的:

*   BigDecimal 的标准规范字符串形式是通过使用不带前导零的字符“0”到“9”转换十进制 BigDecimal 的未缩放值的绝对值而创建的，除非该值为 0，否则使用单个字符“0”。
*   接下来，计算调整后的指数，该指数比将转换后的未缩放值和取反的比例值中的字符数相加少一个。即-scale+(ule gth-1)，其中 ule gth 是以十进制数字表示的未缩放值的绝对值的长度(其精度)。
*   然后，字符形式的指数被加后缀到转换后的未缩放值上(可能会插入小数点)。这包括字母“E”，紧接着是转换成字符形式的调整指数。
*   最后，如果未缩放的值小于零，则整个字符串以减号字符“-”作为前缀。如果未缩放值为零或正，则无符号字符作为前缀。

**语法:**

```
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回这个大十进制数的字符串表示形式。

**覆盖:**此方法覆盖[Java . lang . object](https://www.geeksforgeeks.org/object-class-in-java/)T4。对象类的 toString() 方法。

下面的程序说明了 toString()方法在 java 中的使用

**示例 1:** 将大十进制转换为不带科学符号的字符串的示例

```
// Java program to demonstrate
// toString() method of BigDecimal

import java.math.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating a BigDecimal object
        BigDecimal b;

        // Object of String to hold the number
        String input = "012345678901234567"
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

        // Converting to BigDecimal
        b = new BigDecimal(input);

        // Apply toString() method
        String s = b.toString();

        // Print the result
        System.out.println(s);
    }
}
```

**Output:**

> 1234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901 2345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345543243243624327674637264783 26478326784637264783264736274673864736473246354635463546325645326456325463546536453654632546354653463254653453264564635463263453264654632498739473

**示例 2:** 将大十进制转换为科学符号字符串的示例

```
// Java program to demonstrate
// toString() method of BigDecimal

import java.math.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a BigDecimal object
        BigDecimal a;

        // Create a String object
        String s;

        // Set precision to 5
        MathContext mc
            = new MathContext(5);

        a = new BigDecimal("4536785E4", mc);

        // apply toString() method
        s = a.toString();

        // print the result
        System.out.println(s);
    }
}
```

**Output:**

```
4.5368E+10

```

**参考:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # toString()](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#toString())