# Java 中的十进制格式符号 setCurrency()方法，带示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-set currency-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setcurrency-method-in-java-with-examples/)

**设置货币([货币](https://www.geeksforgeeks.org/java-util-currency-methods-example/) )** 方法 **[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 。Java 中的抽取格式符号类**用于设置该抽取格式符号的区域设置的货币。此方法将货币作为参数并进行设置。

**语法:**

```
public void setCurrency(Currency currency)

```

**参数:**该方法接受**货币**作为参数，该参数是[货币](https://www.geeksforgeeks.org/java-util-currency-methods-example/)，将用于表示该十进制格式符号的货币。

**返回值:**此方法不设置任何内容。

**异常:**如果货币为空，该方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

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

        System.out.println("Current currency: "
                           + dfs.getCurrency());

        Currency currency
            = Currency.getInstance("INR");

        dfs.setCurrency(currency);

        System.out.println("Updated currency: "
                           + dfs.getCurrency());
    }
}
```

**输出:**

```
Current currency: USD
Updated currency: INR

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # setCurrency-Java . util . currency-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setCurrency-java.util.Currency-)