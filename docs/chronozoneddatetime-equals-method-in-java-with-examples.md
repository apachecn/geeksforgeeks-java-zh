# Java 中的 ChronoZonedDateTime 等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-equals-method-in-java-with-examples/)

Java 中**时区数据时间**接口的**等于()**方法用于将该时区数据时间与作为参数传递的另一个日期时间对象进行比较。比较基于偏移日期时间和区域。只有类型为 ChronoZonedDateTime 的对象会相互比较，其他类型会返回 false。此方法返回的值确定如下:

*   Returns true if the time in two time zones is equal.
*   If the two time zones are not equal, false is returned.

**语法:**

```java
boolean equals(Object obj)

```

**参数:**该方法接受单个参数**对象**，该参数代表要与该时区进行比较的对象。这是一个强制参数，不应为空。

**返回值:**如果两个时区的时间相等，则该方法返回 **true** ，否则返回 false。

下面的程序说明了 Java 中的 ChronoZonedDateTime 的 equals()方法:

**程序 1** :

```java
// Program to illustrate the equals() method

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
            System.out.println(dt1.equals(dt));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
true

```

**程序二** :

```java
// Program to illustrate the equals() method

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
            System.out.println(dt1.equals(dt));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
2018-10-25T23:12:31.123+02:00[Europe/Paris]
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
false

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#equals-java.lang.Object-)