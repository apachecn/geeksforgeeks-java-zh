# Java 中的十进制格式符号 getInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-getinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getinstance-method-in-java-with-examples/)

[java.text](https://www.geeksforgeeks.org/tag/java-text-package/) 的 **getInstance()** 方法。[Java 中的抽取格式符号类](https://www.geeksforgeeks.org/tag/java-decimalformatsymbols/)用于获取默认区域设置的抽取格式符号实例。此方法是最终的，不能被覆盖或更改。

**语法:**

```java
public static final
  DdecimalFormatSymbols getInstance()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个带有默认区域设置的**数据格式符号**的实例。

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

        System.out.println("DdecimalFormatSymbols"
                           + " with default Locale: "
                           + dfs.getInstance());
    }
}
```

**输出:**

```java
DdecimalFormatSymbols with default Locale:
 java.text.DecimalFormatSymbols@1073a

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # getInstance–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getInstance--)