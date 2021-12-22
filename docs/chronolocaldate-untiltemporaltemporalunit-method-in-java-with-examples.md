# Java 中的 ChronoLocalDate 直到(时态，临时)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-untltemporaltemporalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-untiltemporaltemporalunit-method-in-java-with-examples/)

**直到()**方法的**时间位置日期**界面用于使用时间单位计算两个时间位置日期对象之间的时间量。起点和终点是这个，指定的 ChronoLocalDate 作为参数传递。如果结束在开始之前，结果将是否定的。该计算返回一个整数，表示两个 ChronoLocalDate 之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 endExclusive，endExclusive 是结束日期，不含，转换为 ChronoLocalDate，单位是计量金额的单位。

**返回值:**该方法返回该时间点日期和结束时间点日期之间的时间量。

**异常:**该方法抛出以下异常:

*   datetime exception–如果无法计算金额，或者结束时态无法转换为计时本地日期。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDate.until() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoLocalDate objects
        ChronoLocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        ChronoLocalDate l2
            = LocalDate
                  .parse("2018-10-25");

        // apply until the method of LocalDate class
        long result
            = l2.until(l1,
                       ChronoUnit.DAYS);

        // print results
        System.out.println("Result in DAYS: "
                           + result);
    }
}
```

**Output:**

```
Result in DAYS: 42

```

**程序 2:**

```
// Java program to demonstrate
// ChronoLocalDate.until() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoLocalDate objects
        ChronoLocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        ChronoLocalDate l2
            = LocalDate
                  .parse("2018-10-25");

        // apply until()
        long result
            = l2.until(l1,
                       ChronoUnit.MONTHS);

        // print results
        System.out.println("Result in MONTHS: "
                           + result);
    }
}
```

**Output:**

```
Result in MONTHS: 1

```

**参考文献:**
[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldata . html #直到-Java . time . temporal . temporal-Java . time . temporal unit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#until-java.time.temporal.Temporal-java.time.temporal.TemporalUnit-)