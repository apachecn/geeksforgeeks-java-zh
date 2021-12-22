# Java 中的十进制样式 toString()方法，示例

> 原文:[https://www . geesforgeks . org/decimal style-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/decimalstyle-tostring-method-in-java-with-example/)

java 中**Java . time . format . DecimalStyle 类**的 **toString()** 方法用来获取这个 decimal style 的字符串值。此方法返回表示字符串值的字符串。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**字符串**，这是这个十进制样式的字符串值。

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

        DecimalStyle ds1
            = DecimalStyle.STANDARD;

        DecimalStyle ds2
            = DecimalStyle.of(
                new Locale("JAPANESE"));

        System.out.println("String value of DS 1: "
                           + ds1.toString());

        System.out.println("String value of DS 2: "
                           + ds2.toString());
    }
}
```

**输出:**

```java
String value of DS 1: DecimalStyle[0+-.]
String value of DS 2: DecimalStyle[0+-.]

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimal style . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#toString())