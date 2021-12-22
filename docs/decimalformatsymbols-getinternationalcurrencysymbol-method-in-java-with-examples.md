# 十进制格式符号 Java 中的 getInternationalCurrencySymbol()方法，带示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-getinternationcurrency symbol-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getinternationalcurrencysymbol-method-in-java-with-examples/)

**getinternationcurrency symbol()**法的 **[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 。Java 中的抽取格式符号类**用于获取用于表示该抽取格式符号的国际货币符号的字符串。此方法返回该十进制格式符号的国际货币符号的 ISO 4217 货币代码。

**语法:**

```
public String getInternationalCurrencySymbol()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回带有默认区域设置的十进制格式符号的国际货币符号的 **ISO 4217 货币代码**。

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

        System.out.println(
            "Character used for"
            + " international currency symbol: "
            + dfs.getInternationalCurrencySymbol());
    }
}
```

**输出:**

```
Character used for international currency symbol: USD

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/text/decimal format symbols . html # getinternational currency symbol--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getInternationalCurrencySymbol--)