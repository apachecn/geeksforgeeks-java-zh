# Java 中的十进制格式符号设置数字(字符)方法，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-setdigitchar-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setdigitchar-method-in-java-with-examples/)

**[的**设置数字(字符)**方法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的[十进制格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)** 用于设置用于表示该十进制格式符号区域设置的数字的字符。此方法将表示数字的字符作为参数。

**语法:**

```java
public void setDigit(char digit)

```

**参数:**该方法接受数字作为参数，该参数是将用于表示该十进制格式符号的数字的字符。

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
                           + " used for digit: "
                           + dfs.getDigit());

        char digit = '*';

        dfs.setDigit(digit);

        System.out.println("Updated Character"
                           + " used for digit: "
                           + dfs.getDigit());
    }
}
```

**输出:**

```java
Current Character used for digit: #
Updated Character used for digit: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # setdigest-char-/a>](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setDigit-char-)