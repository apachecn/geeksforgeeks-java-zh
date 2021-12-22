# Java 中的 ChronoZonedDateTime getZone()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-getzone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-getzone-method-in-java-with-examples/)

**时区数据时间**界面的 **getZone()** 方法用于从该时区数据时间获取时区。此方法返回区域标识，如“亚洲/加尔各答”。

**语法:**

```java
default ZoneId getZone()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个代表时区的**区域标识**。

下面的程序说明了 getZone()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.getZone() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get zone
        ZoneId value = zoneddatetime.getZone();

        // print result
        System.out.println("Time Zone:" + value);
    }
}
```

**输出:**

```java
Time Zone:Asia/Calcutta

```

**程序二:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.getZone() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get zone
        ZoneId value = zoneddatetime.getZone();

        // print result
        System.out.println("Time Zone:" + value);
    }
}
```

**输出:**

```java
Time Zone:Europe/Paris

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # get zone】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#getZone--)