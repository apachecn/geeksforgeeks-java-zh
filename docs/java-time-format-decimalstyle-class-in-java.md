# java 中的 java.time.format.DecimalStyle 类

> 原文:[https://www . geesforgeks . org/Java-time-format-decimal style-class-in-Java/](https://www.geeksforgeeks.org/java-time-format-decimalstyle-class-in-java/)

**Java . time . format . decimal style**类充当访问信息的中心点。处理日期和时间的一个重要部分是本地化。此类提供日期和时间格式中使用的本地化十进制样式。Clone、finalize、getClass、notify、notifyAll、wait 是在这个类中声明的方法。

**语法:**

```
public final class DecimalStyle extends Object
```

**抽取器()方法:**

## Java

```
// Java program to demonstrate the
// Implementation of decimalSeparator()

import java.time.format.*;
import java.util.*;

public class Example1 {
    public static void main(String[] args)
    {

        DecimalStyle x = DecimalStyle.STANDARD;

        System.out.println( "Char before separation: "
            + x.getDecimalSeparator());

        char decimalSeparator = '*';

        DecimalStyle ds = x.withDecimalSeparator( decimalSeparator);

        System.out.println( "Char after separation: "
            + ds.getDecimalSeparator());
    }
}
```

**输出**

```
Char before separation: .
Char after separation: *

```