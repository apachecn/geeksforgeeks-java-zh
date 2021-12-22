# Java 中带有零位数()方法的十进制样式，示例

> 原文:[https://www . geesforgeks . org/decimal style-with zero digital-in-Java-method-with-example/](https://www.geeksforgeeks.org/decimalstyle-withzerodigit-method-in-java-with-example/)

java 中**Java . time . format . DecimalStyle 类**的 **withZeroDigit()** 方法用于为这个 decimal style 的 Locale 设置用来表示零的字符。此方法将字符作为参数，并返回带有更新的负号字符的十进制样式实例。

**语法:**

```java
public void withZeroDigit(char zeroDigit)

```

**参数:**该方法接受**零位数**作为参数，该参数是将用于表示该十进制样式的零的字符。

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

        System.out.println("Current Character"
                           + " used for zero: "
                           + ds.getZeroDigit());

        char zeroDigit = '*';

        ds = ds.withZeroDigit(zeroDigit);

        System.out.println("Updated Character "
                           + "used for zero: "
                           + ds.getZeroDigit());
    }
}
```

**输出:**

```java
Current Character used for zero: 0
Updated Character used for zero: *

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimal style . html # with zero digit(char)](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#withZeroDigit(char))