# Java 中的抽取格式符号 getCurrencySymbol()方法，带示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-getcurrency symbol-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getcurrencysymbol-method-in-java-with-examples/)

**的 **getCurrencySymbol()** 方法。Java 中的抽取格式符号类**用于获取字符串，该字符串用于表示该抽取格式符号的区域设置的货币符号。此方法返回该地区货币符号的字符串。

**语法:**

```java
public String getCurrencySymbol()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个十进制格式符号的货币符号，默认区域设置。

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

        System.out.println("Character used"
                           + " for currency symbol: "
                           + dfs.getCurrencySymbol());
    }
}
```

**输出:**

```java
Character used for currency symbol: $

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/text/decimal format symbols . html # get current cysymbol--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getCurrencySymbol--)