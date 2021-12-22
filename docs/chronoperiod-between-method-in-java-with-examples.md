# Java 中()方法之间的计时周期示例

> 原文:[https://www . geesforgeks . org/chronoperiod-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-between-method-in-java-with-examples/)

Java 中**计时周期界面**的 **between()** 方法用来获取由两个给定日期(包括开始日期和不包括结束日期)之间的年、月、日数组成的计时周期。

该时间周期如下所示:

*   Remove the whole month.
*   Now, calculate the remaining days.
*   Then, make adjustments to ensure that both have the same logo.
*   Now, the number of months is divided into years and months according to the year of 12 months.
*   Consider one month, if the end of the month is greater than or equal to the beginning of the month (for example, from May 12, 2017 to July 18, 2018 is one year, two months and six days).

**注意:**从上面公式得到的计时周期可以是一个*负数*，如果结束在开始之前。负号在每年、每月和每一天都是一样的。

**语法:**

```java
static ChronoPeriod between(ChronoLocalDate startDateInclusive,
                            ChronoLocalDate endDateExclusive)

```

**参数:**

*   **[start date included]** –the start date is included and cannot be blank.
*   **Exclusive end date** –The end date is exclusive and cannot be empty.

**返回值:**计时周期的 between()函数返回给定开始日期和结束日期之间的计时周期。

下面是上面功能的实现:

```java
// Java code to show the chronoPeriod
// between the given start and end date

import java.time.*;
import java.time.chrono.*;

public class ChronoPeriodClass {

    // Function to calculate chronoPeriod between
    // start and end date
    static void
    calculateChronoPeriod(ChronoLocalDate startDate,
                          ChronoLocalDate endDate)
    {
        ChronoPeriod chronoPeriod
            = ChronoPeriod.between(startDate, endDate);
        System.out.println("ChronoPeriod between start and end "
                           + "date is : " + chronoPeriod);
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Start date
        ChronoLocalDate startDate
            = LocalDate.parse("2017-02-13");

        // End date
        ChronoLocalDate endDate
            = LocalDate.parse("2018-08-20");

        calculateChronoPeriod(startDate, endDate);
    }
}
```

**输出:**

```java
ChronoPeriod between start and end date is : P1Y6M7D

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronopodo . html # between-Java . time . cron . chroncaldate-Java . time . chroncaldate-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#between-java.time.chrono.ChronoLocalDate-java.time.chrono.ChronoLocalDate-)