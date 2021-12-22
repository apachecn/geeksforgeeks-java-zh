# Java 中的 chronolocaldatimecomparteto()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-compareto-method-in-java-with-examples/)

Java 方法中**计时本地日期时间**接口的 **compareTo()** 方法将此日期与另一个日期进行比较。

**语法** :

```
default int compareTo(ChronoLocalDateTime other)

```

**参数**:该方法接受一个参数*其他*，该参数指定要比较的其他日期，并且不是特别空。

**返回值**:返回**比较值**，小于则为负，大于则为正。

下面的程序说明了 Java 中的 ChronoLocalDateTime 的 compareTo()方法:

**程序 1** :

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDateTime dt
            = LocalDateTime.parse("2018-12-06T19:21:12");

        System.out.println(dt);

        // Second date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-12-06T19:21:12");

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
2018-12-06T19:21:12
2018-12-06T19:21:12
0

```

**程序二** :

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDateTime dt
            = LocalDateTime.parse("2018-12-05T19:21:12");
        System.out.println(dt);

        // Second date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-12-06T19:21:12");
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
2018-12-05T19:21:12
2018-12-06T19:21:12
1

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chrolcaldatetime . html # share-Java . time . cron . chrolcaldatetime-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#compareTo-java.time.chrono.ChronoLocalDateTime-)