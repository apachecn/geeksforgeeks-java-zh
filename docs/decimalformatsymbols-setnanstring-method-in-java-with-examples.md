# 十进制格式符号 Java 中的 setNaN(字符串)方法，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-setnanstring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setnanstring-method-in-java-with-examples/)

**setNaN(String)** 法**法[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的[抽取格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)** 用于设置字符串，该字符串用于表示该抽取格式符号的区域设置的 NaN。此方法将用于表示 NaN 的字符串作为参数。

**语法:**

```java
public void setNaN(String NaN)

```

**参数:**该方法接受 NaN 作为参数，该参数是将用于表示该十进制格式符号的 NaN 的字符串。

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

        System.out.println("Current String "
                           + "used for NaN: "
                           + dfs.getNaN());

        String NaN = "*";

        dfs.setNaN(NaN);

        System.out.println("Updated String "
                           + "used for NaN: "
                           + dfs.getNaN());
    }
}
```

**输出:**

```java
Current String used for NaN: ?
Updated String used for NaN: *

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # setNaN-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setNaN-java.lang.String-)