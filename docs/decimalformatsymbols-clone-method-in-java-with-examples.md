# 用示例克隆 Java 中的十进制格式符号()方法

> 原文:[https://www . geesforgeks . org/decimal format symbols-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-clone-method-in-java-with-examples/)

**克隆()**法的 **[法的](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的抽取格式符号类**就是用来克隆这个抽取格式符号的。这意味着这个方法将创建另一个十进制格式符号实例，所有属性与这个十进制格式符号相同，并返回它。

**语法:**

```java
public Object clone()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个对象，它是这个十进制格式符号的克隆。

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

        System.out.println("Current DecimalFormatSymbols: "
                           + dfs);

        System.out.println("Cloned DecimalFormatSymbols: "
                           + dfs.clone());
    }
}
```

**输出:**

```java
Current DecimalFormatSymbols: java.text.DecimalFormatSymbols@1073a
Cloned DecimalFormatSymbols: java.text.DecimalFormatSymbols@1073a

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # clone–](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#clone--)