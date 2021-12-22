# Java 中的计时本地日期时间问题支持(临时字段)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-issupportedtemporalfield-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-issupportedtemporalfield-method-in-java-with-examples/)

Java 中**计时本地日期时间接口**的 **isSupported()** 方法检查是否支持指定的临时字段。

**语法:**

```java
default boolean isSupported(TemporalField field)

```

**参数:**该方法接受一个参数*字段*，指定要检查的临时字段，空返回假。

**返回:**如果该日期支持*字段*，则函数返回真，否则返回假。

下面的程序说明了 ChronoLocalDateTime.isSupported()方法:

**程序 1:**

```java
// Program to illustrate
// the isSupported(TemporalField) method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDateTime dt1
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println(dt1);

        System.out.println(
            dt1
                .isSupported(
                    ChronoField.DAY_OF_WEEK));
    }
}
```

**输出:**

```java
2018-11-03T12:45:30
true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html # isSupported-Java . time . temporal field-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#isSupported-java.time.temporal.TemporalField-)