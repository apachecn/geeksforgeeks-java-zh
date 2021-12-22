# Java 中的十进制格式符号 getzerodigital()，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-getzero digit-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getzerodigit-in-java-with-examples/)

**[的 **getZeroDigit()** 方法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的抽取格式符号类**用于获取该抽取格式符号的区域设置中表示零的字符。此方法返回该区域设置的零字符。

**语法:**

```java
public char getZeroDigit()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回这个十进制格式符号的零。

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

        System.out.println("Character used for zero: "
                           + dfs.getZeroDigit());
    }
}
```

**输出:**

```java
Character used for zero: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getZeroDigitDigit–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getZeroDigitDigit--)