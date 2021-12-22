# Java 中的十进制格式符号 setGroupingSeparator()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-setgroupingseparator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setgroupingseparator-method-in-java-with-examples/)

[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的**setgroup separator(char)**方法。[Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)用于设置字符，该字符用于表示该数据格式符号的区域设置的数千个分隔符。此方法将表示千位分隔符的字符作为参数。

**语法:**

```java
public void setGroupingSeparator(char groupingSeparator)

```

**参数:**此方法接受**分组分隔符**作为参数，该参数是将用于表示此数据格式符号的千位分隔符的字符。

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

        System.out.println("Current Character used"
                           + " for thousands separator: "
                           + dfs.getGroupingSeparator());

        char groupingSeparator = '*';

        dfs.setGroupingSeparator(groupingSeparator);

        System.out.println("Updated Character used"
                           + " for thousands separator: "
                           + dfs.getGroupingSeparator());
    }
}
```

**输出:**

```java
Current Character used for thousands separator:,
Updated Character used for thousands separator: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # setgroup ingseparator-char-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setGroupingSeparator-char-)