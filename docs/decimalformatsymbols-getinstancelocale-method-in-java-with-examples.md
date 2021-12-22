# 十进制格式符号 Java 中的 getInstance(Locale)方法，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-getinstance locale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getinstancelocale-method-in-java-with-examples/)

**[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的 **getInstance(Locale)** 方法。Java 中的抽取格式符号类**用于获取指定地区的抽取格式符号实例。此方法是最终的，不能被覆盖或更改。它将需要十进制格式符号的区域设置作为参数，并返回该十进制格式符号的相应实例。

**语法:**

```
public static final DecimalFormatSymbols
    getInstance(Locale locale)

```

**参数:**此方法接受参数 Locale，它是返回十进制格式符号实例的区域设置。

**返回值:**该方法返回具有指定区域设置的十进制格式符号的实例。

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

        Locale locale = new Locale("ENGLISH");

        System.out.println("DecimalFormatSymbols "
                           + "with ENGLISH Locale: "
                           + dfs.getInstance(locale));
    }
}
```

**输出:**

```
DecimalFormatSymbols with ENGLISH Locale:
 java.text.DecimalFormatSymbols@1073a

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getInstance-Java . util . locale-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getInstance-java.util.Locale-)