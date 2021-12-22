# Java 中的抽取格式符号 getDecimalSeparator()方法，带示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-getdecimal separator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getdecimalseparator-method-in-java-with-examples/)

[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的 **getDecimalSeparator()** 方法。[Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)用于获取表示该数据格式符号区域设置的十进制分隔符的字符。此方法返回该区域设置的十进制分隔符的字符。

**语法:**

```
public char getDecimalSeparator()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回数据格式符号的**十进制分隔符**。

**异常:**这个方法不抛出任何异常。

**程序:**

```
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class DecimalFormatSymbolsDemo {
    public static void main(String[] args)
    {

        DecimalFormatSymbols dfs
            = new DecimalFormatSymbols();

        System.out.println("Character used for"
                           + " decimal separator: "
                           + dfs.getDecimalSeparator());
    }
}
```

**输出:**

```
Character used for decimal separator: .

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getdecimals separator–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getDecimalSeparator--)