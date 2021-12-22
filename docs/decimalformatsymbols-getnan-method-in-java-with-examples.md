# Java 中的十进制格式符号 getNaN()方法，带示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-getnan-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getnan-method-in-java-with-examples/)

**getNaN()** 法 **[爪哇](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的[十进制格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)** 用于获取用于表示该十进制格式符号区域设置的 NaN(不是数字)的字符串。此方法返回该地区的 NaN 的字符串。

**语法:**

```
public String getNaN()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回带有默认区域设置的十进制格式符号的安南。

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
                           + " for NaN: "
                           + dfs.getNaN());
    }
}
```

**输出:**

```
Character used for NaN: ?

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getNaN–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getNaN--)