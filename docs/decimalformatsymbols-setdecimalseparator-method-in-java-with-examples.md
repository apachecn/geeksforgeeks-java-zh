# 抽取格式符号在 Java 中设置抽取分离符()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-setdecimal separator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setdecimalseparator-method-in-java-with-examples/)

[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的**set decimal separator(char)**方法。[Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)用于设置字符，该字符用于表示该数据格式符号的区域设置的十进制分隔符。此方法将表示十进制分隔符的字符作为参数。

**语法:**

```java
public void setDecimalSeparator(char decimalSeparator)

```

**参数:**该方法接受**十进制分隔符**作为参数，该参数是用于表示该数据格式符号的十进制分隔符的字符。

**返回值:**此方法不设置任何内容。

**异常:**这个方法不抛出任何异常。

**程序:**

```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class DecimalFormatSymbolsDemo {
    public static void main(String[] args)
    {

        DecimalFormatSymbols dfs
            = new DecimalFormatSymbols();

        System.out.println("Current Character used "
                           + "for decimal separator: "
                           + dfs.getDecimalSeparator());

        char decimalSeparator = '*';

        dfs.setDecimalSeparator(decimalSeparator);

        System.out.println("Updated Character used "
                           + "for decimal separator: "
                           + dfs.getDecimalSeparator());
    }
}
```

**输出:**

```java
Current Character used for decimal separator: .
Updated Character used for decimal separator: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/分米格式符号. html # setdecimal separator-char-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setDecimalSeparator-char-)