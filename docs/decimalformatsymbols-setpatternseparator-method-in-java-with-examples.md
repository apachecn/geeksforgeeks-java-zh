# Java 中的十进制格式符号 setPatternSeparator()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-set patternseparator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setpatternseparator-method-in-java-with-examples/)

**[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的**set pattern parator(char)**方法。Java 中的抽取格式符号类**用于设置字符，该字符用于表示该抽取格式符号的区域设置的模式分隔符。此方法采用用于分隔模式中正负子模式的字符。

**语法:**

```java
public void setPatternSeparator(char patternSeparator)

```

**参数:**此方法接受**模式分隔符**作为参数，该参数是将用于表示此十进制格式符号的模式分隔符的字符。

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

        System.out.println("Current Character"
                           + " used for pattern separator: "
                           + dfs.getPatternSeparator());

        char patternSeparator = '*';

        dfs.setPatternSeparator(patternSeparator);

        System.out.println("Updated Character used "
                           + "for pattern separator: "
                           + dfs.getPatternSeparator());
    }
}
```

**输出:**

```java
Current Character used for pattern separator: ;
Updated Character used for pattern separator: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # set pattern parator-char-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setPatternSeparator-char-)