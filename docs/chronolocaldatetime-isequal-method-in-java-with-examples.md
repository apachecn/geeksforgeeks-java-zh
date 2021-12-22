# Java 中的 chronolocaldatimeisequal()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-isequal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-isequal-method-in-java-with-examples/)

Java 中**chronolocaldetime 接口**的 **isEqual()** 方法用来检查作为参数传递的日期是否等于这个 chronolocaldetime 实例。它返回一个显示相同内容的布尔值。

**语法:**

```
public boolean isEqual(ChronoLocalDateTime otherDate)
```

**参数:**该方法接受一个参数**其他日期**，该参数指定要与该时间地点日期时间进行比较的其他日期时间。它不应为空。

**返回:**该函数返回**布尔值**，显示该日期时间是否等于指定的日期时间。

下面的程序说明了 ChronoLocalDateTime.isEqual()方法:

**程序 1:**

```
// Program to illustrate the isEqual() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        ChronoLocalDateTime dt2
            = LocalDateTime.parse("2016-12-04T12:45:30");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isEqual(dt2));
    }
}
```

**输出:**

```
2018-11-03T12:45:30
2016-12-04T12:45:30
false

```

**程序二:**

```
// Program to illustrate the isEqual() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        ChronoLocalDateTime dt2
            = LocalDateTime.parse("2019-12-04T12:45:30");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isEqual(dt2));
    }
}
```

**输出:**

```
2018-11-03T12:45:30
2019-12-04T12:45:30
false

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chronical datetime . html # isequal-Java . time . cron . chrolcaldatetime-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#isEqual-java.time.chrono.ChronoLocalDateTime-)