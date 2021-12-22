# Java 中的 ChronoZonedDateTime isEqual()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-isequal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-isequal-method-in-java-with-examples/)

Java 中**时区数据时间接口**的 **isEqual()** 方法用于检查作为参数传递的日期是否等于该时区数据时间实例。它返回一个显示相同内容的布尔值。

**语法:**

```java
default boolean isEqual(ChronoZonedDateTime otherDate)
```

**参数:**该方法接受一个参数 **otherDate** ，该参数指定要与该时区数据时间进行比较的其他日期时间。它不应为空。

**返回:**该函数返回**布尔值**，显示该日期时间是否等于指定的日期时间。

下面的程序说明了 ChronoZonedDateTime.isEqual()方法:

**程序 1:**

```java
// Program to illustrate the isEqual() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoZonedDateTime dt1
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        ChronoZonedDateTime dt2
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isEqual(dt2));
    }
}
```

**输出:**

```java
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
true

```

**程序二:**

```java
// Program to illustrate the isEqual() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoZonedDateTime dt1
            = ZonedDateTime.parse(
                "2018-10-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        ChronoZonedDateTime dt2
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isEqual(dt2));
    }
}
```

**输出:**

```java
2018-10-06T19:21:12.123+05:30[Asia/Calcutta]
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
false

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # isequal-Java . time . cron . chronitoredatetime-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#isEqual-java.time.chrono.ChronoZonedDateTime-)