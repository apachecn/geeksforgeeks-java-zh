# 十进制格式符号 Java 中的 setInfinity(字符串)方法示例

> 原文:[https://www . geeksforgeeks . org/decimal format symbols-setinfinitystring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setinfinitystring-method-in-java-with-examples/)

**设置无限(字符串)**的方法**T3。Java 中的[十进制格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)** 用于设置字符串，该字符串用于表示该十进制格式符号的区域设置为无穷大。此方法将表示无穷大的字符串作为参数。

**语法:**

```java
public void setInfinity(String infinity)

```

**参数:**该方法接受无穷大作为参数，该参数是将用于表示该十进制格式符号无穷大的字符串。

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

        System.out.println("Current String"
                           + " used for infinity: "
                           + dfs.getInfinity());

        String infinity = "*";

        dfs.setInfinity(infinity);

        System.out.println("Updated String "
                           + "used for infinity: "
                           + dfs.getInfinity());
    }
}
```

**输出:**

```java
Current String used for infinity: ?
Updated String used for infinity: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # setInfinity-Java . lang . string-/a>](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setInfinity-java.lang.String-)