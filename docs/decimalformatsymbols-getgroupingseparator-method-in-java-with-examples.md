# Java 中的十进制格式符号 getGroupingSeparator()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-getgroup ingseparator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getgroupingseparator-method-in-java-with-examples/)

[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的 **getGroupingSeparator()** 方法。[Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)用于获取字符，该字符用于表示该数据格式符号的区域设置的数千个分隔符。此方法返回该区域设置的千位分隔符的字符。

**语法:**

```
public char getGroupingSeparator()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回数据格式符号的**千位分隔符**。

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
                           + " thousands separator: "
                           + dfs.getGroupingSeparator());
    }
}
```

**输出:**

```
Character used for thousands separator:,

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getgroup ingseparator–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getGroupingSeparator--)