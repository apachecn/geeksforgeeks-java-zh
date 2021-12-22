# Java 中的十进制格式符号 getPercent()方法，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-getpercent-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getpercent-method-in-java-with-examples/)

**[的 **getPercent()** 方法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的[十进制格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)** 用于获取表示该十进制格式符号区域设置的百分号的字符。此方法返回该区域设置的百分号的字符。

**语法:**

```
public char getPercent()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回带有默认区域设置的十进制格式符号的百分号。

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

        System.out.println("Character used"
                           + " for percent sign: "
                           + dfs.getPercent());
    }
}
```

**输出:**

```
Character used for percent sign: %

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/分米格式符号. html # getPercent–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getPercent--)