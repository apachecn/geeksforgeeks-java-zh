# Java 中的大十进制浮点值()方法，带示例

> 原文:[https://www . geesforgeks . org/big decimal-float value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-floatvalue-method-in-java-with-examples/)

T2。floatValue() 将此 BigDecimal 转换为浮点数。如果这个大十进制数值太大，无法表示为浮点数，它将被转换为[浮点数。负 _ 无穷大](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#NEGATIVE_INFINITY)或[浮动。正无限](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#POSITIVE_INFINITY)视情况而定。请注意，即使返回值是有限的，这种转换也会丢失关于 BigDecimal 值精度的信息。

**语法:**

```
public float floatValue()

```

**参数:**此功能不接受参数。

**返回:**该方法返回一个浮点值，该值代表该 BigDecimal 的浮点值。

**例:**

```
Input: BigDecimal1 = 1234
Output: 1234.0

Input: BigDecimal1 = 21545135451354545
Output: 2.15451365E16
Explanation: 
BigInteger1.floatValue() = 2.15451365E16\. 
This BigDecimal is too big 
for a magnitude to represent as a float 
then it will be converted to 
Float.NEGATIVE_INFINITY or 
Float.POSITIVE_INFINITY as appropriate.

```

下面的程序说明了 BigDecimal 类的 floatValue()方法:

**例 1:**

```
// Java program to demonstrate
// floatValue() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // For user input
        // Use Scanner or BufferedReader

        // Object of String created
        // Holds the value
        String input1
            = "545456468445645468464645";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);

        // Using floatValue() method
        float f = a.floatValue();

        // Display the result
        System.out.println(f);
    }
}
```

**输出:**

```
5.4545646E23

```

**例 2:**

```
// Java program to demonstrate
// floatValue() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // For user input
        // Use Scanner or BufferedReader

        // Object of String created
        // Holds the value
        String input1
            = "984522";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);

        // Using floatValue() method
        float f = a.floatValue();

        // Display the result
        System.out.println(f);
    }
}
```

**输出:**

```
984522.0

```

**参考文献:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # float value()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#floatValue())