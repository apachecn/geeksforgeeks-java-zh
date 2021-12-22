# Java 中带有特殊分隔符()方法的十进制样式，示例

> 原文:[https://www . geeksforgeeks . org/decimal style-with decimal separator-method-in-Java-with-example/](https://www.geeksforgeeks.org/decimalstyle-withdecimalseparator-method-in-java-with-example/)

java 中**Java . time . format . DecimalStyle 类**的 **withDecimalSeparator()** 方法用于设置用于表示该 decimal style 区域设置的十进制分隔符的字符。此方法将字符作为参数，并返回带有更新的负号字符的十进制样式实例。

**语法:**

```java
public void withDecimalSeparator(char decimalSeparator)

```

**参数:**该方法接受**十进制分隔符**作为参数，该参数是用于表示该十进制样式的十进制分隔符的字符。

**返回值:**此方法返回带有更新负号字符的十进制样式实例。

**异常:**这个方法不抛出任何异常。

**程序:**

```java
// Java program to demonstrate
// the above method

import java.time.format.*;
import java.util.*;

public class DecimalStyleDemo {
    public static void main(String[] args)
    {

        DecimalStyle ds
            = DecimalStyle.STANDARD;

        System.out.println(
            "Current Character"
            + " used for decimal separator: "
            + ds.getDecimalSeparator());

        char decimalSeparator = '*';

        ds = ds.withDecimalSeparator(
            decimalSeparator);

        System.out.println(
            "Updated Character "
            + "used for decimal separator: "
            + ds.getDecimalSeparator());
    }
}
```

**输出:**

```java
Current Character used for decimal separator: .
Updated Character used for decimal separator: *

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimal style . html # with decimal separator(char)