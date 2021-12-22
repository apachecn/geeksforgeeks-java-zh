# Java 中的十进制格式符号获取指数分隔符()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-getexponent separator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getexponentseparator-method-in-java-with-examples/)

**[的**方法**](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的抽取格式符号类**用于获取字符串，该字符串用于表示该抽取格式符号的区域设置的指数分隔符。此方法返回该地区指数分隔符的字符串。

**语法:**

```
public String getExponentSeparator()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回这个十进制格式符号的指数分隔符。

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
                           + " exponent separator: "
                           + dfs.getExponentSeparator());
    }
}
```

**输出:**

```
Character used for exponent separator: E

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimal formatsymbols . html # getexponent separator–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getExponentSeparator--)