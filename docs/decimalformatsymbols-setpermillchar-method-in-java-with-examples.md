# 十进制格式符号设置 Java 中的 char 方法，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-setpermilchar-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setpermillchar-method-in-java-with-examples/)

[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的 **setPerMill(char)** 方法。[Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)用于设置字符，该字符用于表示这个 DdecimalFormatSymbols 的区域设置的每毫秒符号。此方法将表示每毫秒符号的字符作为参数。

**语法:**

```
public void setPerMill(char perMill)

```

**参数:**该方法接受**参数**作为参数，该参数是用于表示该数据格式符号的每毫秒符号的字符。

**返回值:**此方法不设置任何内容。

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

        System.out.println("Current Character used"
                           + " for per milli sign: "
                           + dfs.getPerMill());

        char perMill = '*';

        dfs.setPerMill(perMill);

        System.out.println("Updated Character used"
                           + " for per milli sign: "
                           + dfs.getPerMill());
    }
}
```

**输出:**

```
Current Character used for per milli sign: ?
Updated Character used for per milli sign: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # setPerMill-char-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setPerMill-char-)