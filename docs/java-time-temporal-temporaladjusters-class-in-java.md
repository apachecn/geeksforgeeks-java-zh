# java 中的 Java . time . temporal adjuster 类

> 原文:[https://www . geesforgeks . org/Java-time-temporal-temporal adjuster-class-in-Java/](https://www.geeksforgeeks.org/java-time-temporal-temporaladjusters-class-in-java/)

Java 中的 TemporalAdjusters 类提供了调整器，这是修改时态对象的关键工具。示例包括设置日期的调整器，如“每月的第二个星期六”或“下星期二”，或者将日期设置为每月的最后一天。

临时调节器有两种使用方式。第一种是通过直接调用接口上的方法。第二种是通过使用时态调整器:

以下两种使用 TemporalAdjuster 的方法是等效的，但建议使用第二种方法，因为它更清晰易读

```
temporal = thisAdjuster.adjustInto(temporal);
temporal = temporal.with(thisAdjuster);
```

**方法**

<figure class="table">

| **方法** | **描述** |
| --- | --- |
| dayOfWeekInMonth（int ordinal， DayOfWeek dayOfWeek） | 此方法用于返回月调整器中的星期几，该调整器返回同一个月内具有第几天的新日期对象。 |
| 第一天每月() | 此方法用于返回“每月第一天”调整器，该调整器返回设置为当月第一天的新日期。 |
| firstDayOfNextMonth() | 此方法用于返回“下月第一天”调整器，该调整器返回设置为下月第一天的新日期。 |
| firstDayOfNextYear() | 此方法用于返回“明年第一天”调整器，该调整器返回设置为明年第一天的新日期。 |
| 第一个工作日() | 此方法用于返回“年初一”调整器，该调整器返回设置为当年年初一的新日期。 |
| firstInMonth（DayOfWeek DayOfWeek） | 此方法用于返回月内第一个调整器，该调整器返回与第一个匹配的星期几在同一个月中的新日期。 |
| 最后一天 | 此方法用于返回“每月的最后一天”调整器，该调整器返回设置为当月最后一天的新日期。 |
| lastDayOfYear() | 此方法用于返回“一年中的最后一天”调整器，该调整器返回一个设置为当年最后一天的新日期。 |
| 上一月（星期一星期一） | 此方法用于返回月中最后一个调整器，该调整器返回与最后一个匹配的星期几在同一个月中的新日期。 |
| 下一个（星期一星期一星期） | 此方法用于返回下一个星期几调整器，该调整器将日期调整到被调整日期之后指定星期几的第一次出现。 |
| 下一个或 Same（星期一星期一星期） | 此方法用于返回下一个或同一天的星期调整器，该调整器将日期调整到正在调整的日期之后指定星期的第一次出现，除非它已经在返回相同对象的那一天。 |
| 数据调节器(非数据调节器<localdate>日期基准数据调节器)</localdate> | 此方法用于获取包装日期调整器的临时调整器。 |
| 上一个（星期一星期一） | 此方法用于返回前一个星期几调整器，该调整器将日期调整到被调整日期之前指定星期几的第一次出现。 |
| 上一页或 Same（星期几星期一） | 此方法用于返回前一个或同一天的星期调整器，该调整器将日期调整到被调整日期之前的指定星期的第一次出现，除非它已经在返回相同对象的那一天。 |

</figure>

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Implementation of TemporalAdjuster Class Output will
// be different at the time of execution for different
// days. All the dates in the output will be with respect
// to the current date of executing the program

import java.time.DayOfWeek;
import java.time.LocalDate;
import java.time.temporal.TemporalAdjusters;

public class TemporalAdjusterExample {
    public static void main(String args[])
    {
        TemporalAdjusterExample gfg
            = new TemporalAdjusterExample();
        gfg.testAdjusters();
    }

    public void testAdjusters()
    {
        // to get the current date
        LocalDate date1 = LocalDate.now();
        System.out.println("Today's date is: " + date1);

        // to get the next monday
        LocalDate nextTuesday = date1.with(
            TemporalAdjusters.next(DayOfWeek.MONDAY));
        System.out.println("Next Monday is on : "
                           + nextTuesday);

        // to get the second saturday of next month
        LocalDate firstInYear = LocalDate.of(
            date1.getYear(), date1.getMonth(), 1);

        LocalDate secondSaturday
            = firstInYear
                  .with(TemporalAdjusters.nextOrSame(
                      DayOfWeek.SATURDAY))
                  .with(TemporalAdjusters.next(
                      DayOfWeek.SATURDAY));

        // print date of second Saturday of next month
        System.out.println("Second saturday is on : "
                           + secondSaturday);
    }
}
```

**输出:**

```
Today's date is: 2021-02-24
Next Monday is on : 2021-03-01
Second saturday is on : 2021-02-13
```