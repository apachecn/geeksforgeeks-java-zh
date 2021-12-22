# Java 中 BigDecimal toEngineeringString()方法，带示例

> 原文:[https://www . geesforgeks . org/big decimal-to engineeringstring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-toengineeringstring-method-in-java-with-examples/)

T2。toEngineeringString() 方法用于表示当前的 BigDecimal，如果需要指数，则使用工程符号将该方法调用为字符串形式。BigDecimal 的字符串表示与 [toString()](https://www.geeksforgeeks.org/bigdecimal-tostring-method-in-java-with-examples/) 方法中描述的相同，只是如果使用指数表示法，十的幂被调整为三的倍数(工程表示法)，这样非零值的整数部分将在 1 到 999 的范围内。
**语法:**

```
public String toEngineeringString()

```

**参数:**该方法不接受任何参数。
**返回值:**这个方法返回这个大十进制数的工程字符串表示。

下面的程序说明了如何在 java 中使用 toEngineeringString()方法
**示例 1:** 示例将 BigDecimal 转换为无指数符号的工程字符串

```
// Java program to demonstrate
// toEngineeringString() method of BigDecimal

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
                       + "4635463263453264"
                       + "654632498739473";

        // Converting to BigDecimal
        b = new BigDecimal(input);

        // Apply toEngineeringString() method
        String s = b.toEngineeringString();

        // Print the result
        System.out.println(s);
    }
}
```

**Output:**

> 1234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901 2345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345543243243624327674637264783 26478326784637264784635463263453264654632498739473

**例 2:** 用指数表示法将 BigDecimal 转换为工程字符串的示例

```
// Java program to demonstrate
// toEngineeringString() method of BigDecimal

import java.math.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a BigDecimal object
        BigDecimal a = new BigDecimal("4536785E10");

        // Create a String object
        String s;

        // apply toEngineeringString() method
        s = a.toEngineeringString();

        // print the result
        System.out.println(s);
    }
}
```

**Output:**

> 45.36785E+15

**参考文献:**[https://docs . Oracle . com/en/Java/javase/12/docs/API/Java . base/Java/math/bigdecimal . html # to engineereingstring()](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#toEngineeringString())