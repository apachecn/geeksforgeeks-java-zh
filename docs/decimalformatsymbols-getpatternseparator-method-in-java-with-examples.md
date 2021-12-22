# Java 中的十进制格式符号 getPatternSeparator()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-getpatternseparator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getpatternseparator-method-in-java-with-examples/)

**GetPatternseParator()**的**方法的 [java.text。Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-text-package/)**用于获取表示该抽取格式符号区域设置的模式分隔符的字符。此方法返回用于分隔模式中正负子模式的字符。

**语法:**

```
public char getPatternSeparator()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回带有区域设置的十进制格式符号的模式分隔符。

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

        System.out.println("Character used "
                           + "for pattern separator: "
                           + dfs.getPatternSeparator());
    }
}
```

**输出:**

```
Character used for pattern separator: ;

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getPatternSeparator–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getPatternSeparator--)