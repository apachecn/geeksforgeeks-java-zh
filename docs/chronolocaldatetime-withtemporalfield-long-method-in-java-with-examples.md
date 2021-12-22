# Java 中带有(TemporalField，long)方法的 ChronoLocalDateTime，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-with temporal field-long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-withtemporalfield-long-method-in-java-with-examples/)

**计时本地日期时间**界面的 **with(临时字段，长新值)**方法用于将计时本地日期时间的指定字段设置为新值，并返回新时间的副本。此方法可用于更改任何支持的字段，如年、日、月、小时、分钟或秒。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。ChronoLocalDateTime 的这个实例是不可变的，不受此方法调用的影响。

**语法:**

```java
ChronoLocalDateTime with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法基于此返回一个设置了指定字段的 ChronoLocalDateTime。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** -If it cannot be adjusted.
*   不受支持的 dtime type exception 唉哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟。
*   **Arithmetic exception** -If there is a numerical overflow.

下面的程序说明了 with()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // print instance
        System.out.println("ChronoLocalDateTime before"
                           + " adjustment: "
                           + time);

        // apply with method of ChronoLocalDateTime
        ChronoLocalDateTime updatedlocal
            = time.with(ChronoField.YEAR, 2017);

        // print instance
        System.out.println("ChronoLocalDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**输出:**

```java
ChronoLocalDateTime before adjustment: 2019-12-31T19:15:30
ChronoLocalDateTime after adjustment: 2017-12-31T19:15:30

```

**程序二:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime
                  .parse("2018-10-25T23:12:31.123");

        // print instance
        System.out.println("ChronoLocalDateTime before"
                           + " adjustment: "
                           + time);

        // apply with method of ChronoLocalDateTime
        ChronoLocalDateTime updatedlocal
            = time.with(ChronoField.MONTH_OF_YEAR, 1);

        // print instance
        System.out.println("ChronoLocalDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**输出:**

```java
ChronoLocalDateTime before adjustment: 2018-10-25T23:12:31.123
ChronoLocalDateTime after adjustment: 2018-01-25T23:12:31.123

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html # with-Java . time . temporal field-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#with-java.time.temporal.TemporalField-long-)