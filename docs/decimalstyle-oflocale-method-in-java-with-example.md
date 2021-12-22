# Java 中(Locale)方法的十进制样式，示例

> 原文:[https://www . geeksforgeeks . org/decimal style-of locale-method-in-Java-with-example/](https://www.geeksforgeeks.org/decimalstyle-oflocale-method-in-java-with-example/)

java 中**Java . time . format . DecimalStyle 类**的【Locale】方法的**用于获取指定区域的 decimal style 实例。**

**语法:**

```
public static DecimalStyle of(Locale locale)

```

**参数:**该方法接受一个参数**区域**，该参数需要这个十进制样式。

**返回值:**该方法返回指定区域设置的**十进制样式**实例。

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

        Locale locale = new Locale("ENGLISH");

        System.out.println("DecimalStyle for "
                           + locale + " locale: "
                           + ds.of(locale));
    }
}
```

**输出:**

```
DecimalStyle for english locale: DecimalStyle[0+-.]

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimal style . html # of(Java . util . locale)](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#of(java.util.Locale))