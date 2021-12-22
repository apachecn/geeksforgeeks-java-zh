# Java 中的十进制格式符号 getPerMill()方法，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-getpermill-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getpermill-method-in-java-with-examples/)

[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的 **getPerMill()** 方法。[Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)用于获取字符，该字符用于表示这个 DdecimalFormatSymbols 的 Locale 的每毫秒符号。此方法返回该区域设置的每毫秒字符数。

**语法:**

```java
public char getPerMill()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回数据格式符号的每毫符号的**。**

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

        System.out.println("Character used for"
                           + " per milli sign: "
                           + dfs.getPerMill());
    }
}
```

**输出:**

```java
Character used for per milli sign: ?

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getPerMill–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getPerMill--)