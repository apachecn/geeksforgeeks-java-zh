# Java 中的十进制样式 getPositiveSign()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal style-getpositivesign-method-in-Java-with-example/](https://www.geeksforgeeks.org/decimalstyle-getpositivesign-method-in-java-with-example/)

java 中**Java . time . format . DecimalStyle 类**的 **getPositiveSign()** 方法用于获取用于表示该 decimal style 的 Locale 的正号的字符。此方法返回该区域设置的正号字符。

**语法:**

```
public char getPositiveSign()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**字符**，代表这个十进制样式的正号。

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

        System.out.println("Character used "
                           + "for positive sign: "
                           + ds.getPositiveSign());
    }
}
```

**输出:**

```
Character used for positive sign: +

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimals style . html # getPositiveSign()](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#getPositiveSign())