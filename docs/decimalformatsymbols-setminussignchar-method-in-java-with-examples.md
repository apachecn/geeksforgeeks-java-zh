# 十进制格式符号在 Java 中设置符号(字符)方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-setminssignchar-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setminussignchar-method-in-java-with-examples/)

**设置**的**方法。Java 中的抽取格式符号类**用于设置该抽取格式符号的区域设置的负号字符。此方法将表示减号的字符作为参数。

**语法:**

```
public void setMinusSign(char minusSign)

```

**参数:**该方法接受**符号**作为参数，该参数是用于表示该十进制格式符号负号的字符。

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
                           + " for minus sign: "
                           + dfs.getMinusSign());

        char minusSign = '*';

        dfs.setMinusSign(minusSign);

        System.out.println("Updated Character used"
                           + " for minus sign: "
                           + dfs.getMinusSign());
    }
}
```

**输出:**

```
Current Character used for minus sign: -
Updated Character used for minus sign: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/分米格式符号. html # getminsign–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getMinusSign--)