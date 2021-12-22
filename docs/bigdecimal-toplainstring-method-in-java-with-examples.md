# Java 中的 BigDecimal toPlainString()方法，带示例

> 原文:[https://www . geesforgeks . org/big decimal-toplainstring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-toplainstring-method-in-java-with-examples/)

T2。toPlainString() 方法用于表示当前的 BigDecimal，通过该方法将该方法调用为不带指数字段的 String 形式。如果数值为正刻度，小数点右边的位数用于表示刻度。对于具有零刻度或负刻度的值，生成的结果字符串就好像该值被转换为具有零刻度的数值相等的值，并且好像零刻度值的所有尾随零都出现在结果中。
**注:**如果将此方法的结果传递给[字符串](https://www.geeksforgeeks.org/strings-in-java/)构造函数，则只会恢复此 BigDecimal 的数值，新 BigDecimal 的表示可能会有不同的小数位数。特别是，该方法的行为类似于[到字符串](https://www.geeksforgeeks.org/object-tostring-method-in-java/)方法。

**语法:**

```
public String toPlainString()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回这个没有指数字段的大十进制数的字符串表示形式。

下面的程序说明了 toPlainString()方法在 java 中的使用

**示例 1:** 将大十进制转换为不带指数符号的普通字符串的示例

```
// Java program to demonstrate
// toPlainString() method of BigDecimal

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

        // Apply toPlainString() method
        String s = b.toPlainString();

        // Print the result
        System.out.println(s);
    }
}
```

**Output:**

> 1234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901 2345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345543243243624327674637264783 26478326784637264783264736274673864736473246354635463546325645326456325463546536453654632546354653463254653453264564635463263453264654632498739473

**示例 2:** 将大十进制转换为指数符号的普通字符串的示例

```
// Java program to demonstrate
// toPlainString() method of BigDecimal

import java.math.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a BigDecimal object
        BigDecimal a;

        // Create a String object
        String s;

        a = new BigDecimal("4536785E10");

        // apply toPlainString() method
        s = a.toPlainString();

        // print the result
        System.out.println(s);
    }
}
```

**Output:**

> 45367850000000000

**参考文献:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # toPlainString()](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#toPlainString())