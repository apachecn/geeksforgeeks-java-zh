# Java 中的十进制格式符号设置零位数()方法，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-set zero digit-in-Java-method-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setzerodigit-method-in-java-with-examples/)

[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的**设置零位数(char)** 方法。[Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)用于设置字符，该字符用于表示该数据格式符号的区域设置为零。此方法将字符作为参数。

**语法:**

```java
public void setZeroDigit(char zeroDigit)

```

**参数:**该方法接受**零位数**作为参数，该参数是用于表示该数据格式符号的零的字符。

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
                           + " used for zero: "
                           + dfs.getZeroDigit());

        char zeroDigit = '*';

        dfs.setZeroDigit(zeroDigit);

        System.out.println("Updated Character "
                           + "used for zero: "
                           + dfs.getZeroDigit());
    }
}
```

**输出:**

```java
Current Character used for zero: 0
Updated Character used for zero: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # setzerodigital-char-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setZeroDigit-char-)