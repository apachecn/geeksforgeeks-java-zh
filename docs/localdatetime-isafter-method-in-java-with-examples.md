# Java 中的 LocalDateTime isAfter()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-is after-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-isafter-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的**isaafter()**方法用于检查作为参数传递的日期是否在这个 LocalDateTime 实例之后。它返回一个显示相同内容的布尔值。

**语法:**

```
public boolean isAfter(ChronoLocalDateTime otherDate)
```

**参数:**该方法接受一个参数 **otherDate** ，该参数指定要与该本地日期时间进行比较的另一个日期时间。它不应为空。

**返回:**该函数返回**布尔值**，显示该日期时间是否在指定的日期时间之后。

下面的程序说明了 LocalDateTime.isAfter()方法:

**程序 1:**

```
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime.parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        LocalDateTime dt2
            = LocalDateTime.parse("2016-12-04T12:45:30");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isAfter(dt2));
    }
}
```

**输出:**

```
2018-11-03T12:45:30
2016-12-04T12:45:30
true

```

**程序二:**

```
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime.parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        LocalDateTime dt2
            = LocalDateTime.parse("2019-12-04T12:45:30");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isAfter(dt2));
    }
}
```

**输出:**

```
2018-11-03T12:45:30
2019-12-04T12:45:30
false

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/local datetime . html # isaafter(Java . time . cron . chrolcaldatetime)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#isAfter(java.time.chrono.ChronoLocalDateTime))