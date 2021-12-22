# Java 中的十进制格式符号集合指数分隔符()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-setexp 指数 separator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setexponentseparator-method-in-java-with-examples/)

**[的**设置指数分隔符(字符串)**方法。Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-text-package/)**用于设置字符串，该字符串用于表示该抽取格式符号的区域设置的指数分隔符。此方法将表示指数分隔符的字符串作为参数。

**语法:**

```java
public void setExponentSeparator(
            String exponentSeparator)

```

**参数:**此方法接受指数分隔符作为参数，该参数是将用于表示此十进制格式符号的指数分隔符的字符串。

**返回值:**此方法不设置任何内容。

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

        System.out.println("Current String used "
                           + "for exponent separator: "
                           + dfs.getExponentSeparator());

        String exponentSeparator = "*";

        dfs.setExponentSeparator(exponentSeparator);

        System.out.println("Updated String used for"
                           + " exponent separator: "
                           + dfs.getExponentSeparator());
    }
}
```

**输出:**

```java
Current String used for exponent separator: E
Updated String used for exponent separator: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimal formatsymbols . html # setindexentseparator-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setExponentSeparator-java.lang.String-)