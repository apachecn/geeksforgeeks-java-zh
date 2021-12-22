# Java 中的十进制格式符号 getMinusSign()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-getminsign-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getminussign-method-in-java-with-examples/)

**[的**getminsign()**方法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的抽取格式符号类**用于获取该抽取格式符号的区域设置的负号字符。此方法返回该区域设置的减号字符。

**语法:**

```java
public char getMinusSign()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回带有默认区域设置的十进制格式符号的负号。

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
                           + " for minus sign: "
                           + dfs.getMinusSign());
    }
}
```

**输出:**

```java
Character used for minus sign: -

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getminsign–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getMinusSign--)