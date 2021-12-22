# Java 中的 ChronoZonedDateTime 格式()方法，带示例

> 原文:[https://www . geesforgeks . org/chronozoneddatetime-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-format-method-in-java-with-examples/)

Java 中**时空数据**接口的 **format()** 方法用于使用作为参数传递的指定格式化程序格式化该日期时间。该日期时间将被传递给格式化程序以生成一个字符串。

**语法:**

```java
default String format(DateTimeFormatter formatter)

```

**参数:**该方法接受单个参数**格式化程序**，表示要使用的格式化程序。这是一个强制参数，不应为空。

**返回值:**这个方法返回一个**字符串**代表格式化的日期时间字符串。

**异常:**如果打印过程中出现错误，该方法将抛出**日期时间异常**。

下面的程序说明了格式()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.format() method

import java.time.*;
import java.time.chrono.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime objects
        ChronoZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // create a formatter
        DateTimeFormatter formatter
            = DateTimeFormatter.ISO_TIME;

        // apply format()
        String value
            = zoneddatetime.format(formatter);

        // print result
        System.out.println("Result: " + value);
    }
}
```

**Output:**

```java
Result: 19:21:12.123+05:30

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.format() method

import java.time.*;
import java.time.chrono.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime objects
        ChronoZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // create a formatter
        DateTimeFormatter formatter
            = DateTimeFormatter.BASIC_ISO_DATE;

        // apply format()
        String value
            = zoneddatetime.format(formatter);

        // print result
        System.out.println("Result: " + value);
    }
}
```

**Output:**

```java
Result: 20181025+0200

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html # format-Java . time . format . datetime formatter-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#format-java.time.format.DateTimeFormatter-)