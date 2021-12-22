# 十进制格式符号获取 Java 中的 monetary 十进制分离符()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-getmonearydecimal separator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getmonetarydecimalseparator-method-in-java-with-examples/)

**[的](https://www.geeksforgeeks.org/tag/java-text-package/)**方法。Java 中的抽取格式符号类用于获取用于表示该抽取格式符号区域设置的货币小数分隔符的字符。此方法返回该地区货币小数分隔符的字符。

**语法:**

```
public char getMonetaryDecimalSeparator()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回这个十进制格式符号的货币小数分隔符。

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
                           + " monetary decimal separator: "
                           + dfs.getMonetaryDecimalSeparator());
    }
}
```

**输出:**

```
Character used for monetary decimal separator: .

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getmonetary decimal separator–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getMonetaryDecimalSeparator--)