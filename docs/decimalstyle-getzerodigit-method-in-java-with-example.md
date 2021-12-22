# Java 中的十进制样式 getZeroDigit()方法，示例

> 原文:[https://www . geesforgeks . org/decimal style-getzero digit-in-Java-method-with-example/](https://www.geeksforgeeks.org/decimalstyle-getzerodigit-method-in-java-with-example/)

java 中的**Java . time . format . DecimalStyle 类**的**getzerodigest()**方法用于获取这个 decimal style 的 Locale 用来表示零的字符。此方法返回该区域设置的零字符。

**语法:**

```
public char getZeroDigit()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**字符**，代表这个十进制样式的零。

**异常:**这个方法不抛出任何异常。

**程序:**

```
// Java program to demonstrate
// the above method

import java.time.format.*;
import java.util.*;

public class DecimalStyleDemo {
    public static void main(String[] args)
    {

        DecimalStyle ds
            = DecimalStyle.STANDARD;

        System.out.println("Character used"
                           + " for zero: "
                           + ds.getZeroDigit());
    }
}
```

**输出:**

```
Character used for zero: 0

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimal style . html # getZeroDigit()](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#getZeroDigit())