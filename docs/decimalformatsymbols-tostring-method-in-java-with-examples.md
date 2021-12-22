# Java 中的十进制格式符号 toString()方法，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-tostring-method-in-java-with-examples/)

**toString()** 法的 **[爪哇](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的抽取格式符号类**用来获取这个抽取格式符号的字符串值。此方法返回一个表示字符串值的整数。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个字符串，它是这个十进制格式符号的字符串值。

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

        System.out.println("DecimalFormatSymbols: "
                           + dfs);

        System.out.println("String value: "
                           + dfs.toString());
    }
}
```

**输出:**

```java
DecimalFormatSymbols: java.text.DecimalFormatSymbols@1073a
String value: java.text.DecimalFormatSymbols@1073a

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/object . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/lang/Object.html#toString--)