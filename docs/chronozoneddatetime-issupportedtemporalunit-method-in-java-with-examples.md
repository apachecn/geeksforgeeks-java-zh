# Java 中的时区数据时间问题支持的方法，示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-issupportedtemporalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-issupportedtemporalunit-method-in-java-with-examples/)

Java 中**时区数据时间接口**的 **isSupported()** 方法检查是否支持指定的时间单位。

**语法:**

```java
default boolean isSupported(TemporalUnit unit)

```

**参数:**该方法接受一个参数*单位*，指定要检查的时间单位，空返回假。

**返回:**如果该日期支持*单位*，则函数返回真，否则返回假。

下面的程序说明了时区数据时间.问题支持()方法:

**程序 1:**

```java
// Program to illustrate the
// isSupported(TemporalUnit) method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoZonedDateTime dt1
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Prints the date
        System.out.println(dt1);

        System.out.println(dt1.isSupported(ChronoUnit.DAYS));
    }
}
```

**输出:**

```java
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html # isSupported-Java . time . temporalunit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#isSupported-java.time.temporal.TemporalUnit-)