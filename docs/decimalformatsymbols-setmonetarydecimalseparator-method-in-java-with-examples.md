# 十进制格式符号设置 Java 中的 monetary 十进制分离符()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-setmonearydecimal separator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setmonetarydecimalseparator-method-in-java-with-examples/)

**设置**的**方法。Java 中的十进制格式符号类**用于设置字符，该字符用于表示该十进制格式符号的区域设置的货币小数分隔符。此方法将表示货币小数分隔符的字符作为参数。

**语法:**

```java
public void setMonetaryDecimalSeparator(char monetaryDecimalSeparator)

```

**参数:**该方法接受**货币十进制分隔符**作为参数，该参数是用于表示该十进制格式符号的货币十进制分隔符的字符。

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

        System.out.println("Current Character used"
                           + " for monetary decimal separator: "
                           + dfs.getMonetaryDecimalSeparator());

        char monetaryDecimalSeparator = '*';

        dfs.setMonetaryDecimalSeparator(
            monetaryDecimalSeparator);

        System.out.println("Updated Character used"
                           + " for monetary decimal separator: "
                           + dfs.getMonetaryDecimalSeparator());
    }
}
```

**输出:**

```java
Current Character used for monetary decimal separator: .
Updated Character used for monetary decimal separator: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # setmonearydecimal separator-char-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setMonetaryDecimalSeparator-char-)