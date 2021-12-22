# Java 中的 ChronoZonedDateTime compareTo()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-compareto-method-in-java-with-examples/)

Java 方法中**时区数据时间**接口的 **compareTo()** 方法将此日期与另一个日期进行比较。

**语法** :

```
default int compareTo(ChronoZonedDateTime other)

```

**参数**:该方法接受一个参数*其他*，该参数指定要比较的其他日期，并且不是特别空。

**返回值**:它返回比较器值，比较器值小则为负，大则为正。

下面的程序说明了 Java 中的 ChronoZonedDateTime 的 compareTo()方法:

**节目 1** :

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoZonedDateTime dt
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        System.out.println(dt);

        // Second date
        ChronoZonedDateTime dt1
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        System.out.println(dt1);

        try {
            // Compare both dates
            System.out.println(dt1.compareTo(dt));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
0

```

**节目 2** :

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoZonedDateTime dt
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        System.out.println(dt);

        // Second date
        ChronoZonedDateTime dt1
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        System.out.println(dt1);

        try {
            // Compare both dates
            System.out.println(dt1.compareTo(dt));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
2018-10-25T23:12:31.123+02:00[Europe/Paris]
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
1

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # share-Java . time . chrono . chronitoredatetime-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#compareTo-java.time.chrono.ChronoZonedDateTime-)