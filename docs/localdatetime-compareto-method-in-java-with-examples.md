# Java 中的 LocalDateTime compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-compareto-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的 **compareTo()** 方法用于将该日期时间与作为参数传递的日期时间进行比较。

**语法:**

```
public int compareTo(ChronoLocalDateTime anotherDate)

```

**参数:**该方法接受一个参数**另一个日期**，该参数指定要比较的另一个日期时间。它不应为空。

**返回:**该函数返回一个**整数值**，这是比较后的比较值。

下面的程序说明了 LocalDateTime.compareTo()方法:

**程序 1:**

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println("Date 1: " + dt1);

        // Parses the date
        LocalDateTime dt2
            = LocalDateTime
                  .parse("2015-01-05T12:45:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares the date
        System.out.println("After comparison: "
                           + dt2.compareTo(dt1));
    }
}
```

**输出:**

```
Date 1: 2018-11-03T12:45:30
Date 2: 2015-01-05T12:45:30
After comparison: -3

```

**程序二:**

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2010-12-05T12:50:30");

        // Prints the date
        System.out.println("Date 1: " + dt1);

        // Parses the date
        LocalDateTime dt2
            = LocalDateTime
                  .parse("2012-05-10T12:50:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares the date
        System.out.println("After comparison: "
                           + dt2.compareTo(dt1));
    }
}
```

**输出:**

```
Date 1: 2010-12-05T12:50:30
Date 2: 2012-05-10T12:50:30
After comparison: 2

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/local datetime . html # share(Java . time . cron . chrolcaldatetime)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#compareTo(java.time.chrono.ChronoLocalDateTime))