# Java 中的 ChronoZonedDateTime 直到()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-until-method-in-java-with-examples/)

**时区数据时间**界面的**直到()**方法用于使用时间单位计算两个时区数据时间对象之间的时间量。起点和终点都是这个，指定的时区时间作为参数传递。如果结束在开始之前，结果将是否定的。计算返回一个整数，表示两个时区之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **endExclusive** :为结束日期，不含，转换为时区数据时间
*   **单位**:是计量金额的单位。

**返回值:**此方法返回此时区数据时间与结束时区数据时间之间的时间量。

**异常:**该方法抛出以下异常:

*   datetime exception–如果无法计算金额，或者结束时间无法转换为时区数据时间。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.until() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoZonedDateTime objects
        ChronoZonedDateTime z1
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        ChronoZonedDateTime z2
            = ZonedDateTime
                  .parse(
                      "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // apply until method of ChronoZonedDateTime class
        long result
            = z1.until(z2,
                       ChronoUnit.HOURS);

        // print results
        System.out.println("Result in HOURS: "
                           + result);
    }
}
```

**Output:**

```java
Result in HOURS: -1000

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.until() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoZonedDateTime objects
        ChronoZonedDateTime z1
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        ChronoZonedDateTime z2
            = ZonedDateTime
                  .parse(
                      "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // applynedDateTime.parseChronoZonedDateTime class
        long result
            = z2.until(z1,
                       ChronoUnit.DAYS);

        // print results
        System.out.println("Result in DAYS: "
                           + result);
    }
}
```

**Output:**

```java
Result in DAYS: 41

```

**参考文献:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/temporal . html #直到-Java . time . temporal . temporal-Java . time . temporal unit-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/Temporal.html#until-java.time.temporal.Temporal-java.time.temporal.TemporalUnit-)