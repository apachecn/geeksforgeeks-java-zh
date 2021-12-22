# Java 中的 ChronoLocalDateTime 直到()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-until-method-in-java-with-examples/)

**直到()**方法的**计时本地日期时间**界面用于计算两个计时本地日期时间对象之间的时间量使用时间单位。开始点和结束点是这样的，指定的 ChronoLocalDateTime 作为参数传递。如果结束在开始之前，结果将是否定的。该计算返回一个整数，表示两个 ChronoLocalDateTime 之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public long until(Temporal endExclusive, 
                  TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **endExclusive** 是结束日期，不包括在内，它被转换为一个 ChronoLocalDateTime，并且
*   **单位**，是计量金额的单位。

**返回值:**该方法返回该时间点日期时间和结束时间点日期时间之间的**时间量**。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果金额无法计算，或者结束时间无法转换为时间位置日期时间。
*   **不支持的 temporaltypexception**–如果不支持该设备。
*   **算术异常**–如果出现数值溢出。

以下程序说明了直到()方法:
**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDateTime.until() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoLocalDateTime objects
        ChronoLocalDateTime z1
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        ChronoLocalDateTime z2
            = LocalDateTime.parse(
                "2018-10-25T23:12:31.123");

        // apply until method of ChronoLocalDateTime class
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

```
Result in HOURS: -10364

```

**程序 2:**

```
// Java program to demonstrate
// ChronoLocalDateTime.until() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoLocalDateTime objects
        ChronoLocalDateTime z1
            = LocalDateTime
                  .parse("1999-10-31T19:15:30");

        ChronoLocalDateTime z2
            = LocalDateTime.parse(
                "1990-10-25T23:12:31.123");

        // applynedDateTime.parseChronoLocalDateTime class
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

```
Result in DAYS: 3292

```

**参考文献:**
[https://docs . Oracle . com/javase/9/docs/API/Java/time/temporal . html #直到-java.time .时态. temporal-Java . time . temporal unit-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/Temporal.html#until-java.time.temporal.Temporal-java.time.temporal.TemporalUnit-)