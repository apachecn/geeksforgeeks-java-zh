# Java 中的十进制格式符号 getInfinity()方法，带示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-getinfinity-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getinfinity-method-in-java-with-examples/)

**[的**方法**](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的[十进制格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)** 用于获取字符串，该字符串用于表示该十进制格式符号的区域设置为无穷大。此方法返回该区域无限的字符串。

**语法:**

```
public String getInfinity()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个无限的十进制格式符号和默认的区域设置。

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
                           + " for infinity: "
                           + dfs.getInfinity());
    }
}
```

**输出:**

```
Character used for infinity: ?

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/分米格式符号. html # GetInfinity–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getInfinity--)