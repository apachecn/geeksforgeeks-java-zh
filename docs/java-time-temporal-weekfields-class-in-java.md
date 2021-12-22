# java 中的 java.time.temporal.WeekFields 类

> 原文:[https://www . geesforgeks . org/Java-time-temporal-weekfield-class-in-Java/](https://www.geeksforgeeks.org/java-time-temporal-weekfields-class-in-java/)

**周字段**类表示周的定义，以提供临时字段实例。WeekFields 提供了五个字段，weekOfYear()、weekOfMonth()、dayOfWeek()、weekOfWeekBasedYear()和 weekBasedYear()，它们提供了对任何时态对象的值的访问。

每个不同的周字段都需要一个单独的字段实例，并且需要:

*   一周开始
*   最短天数

**类申报:**

```
public final class WeekFields
extends Object
implements Serializable
```

**WeekFields 类从 java.lang.Object 类继承了以下方法****:**

*   克隆()
*   最终确定()
*   getClass()
*   通知()
*   notifyAll()
*   等待()

**周字段类的方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 星期（） | 此方法返回一个字段，以基于此周字段访问一周中的某一天。 |
| 等于(对象对象) | 此方法检查该周字段是否等于指定的对象。 |
| getFirstDayOfWeek() | 此方法获取一周的第一天。 |
| getMinimalDaysInFirstWeek() | 此方法在第一周获取最少天数。 |
| hashCode() | 此方法返回此 WeekFields 的哈希代码。 |
| of(第一个星期，第一个星期) | 此方法从一周的第一天和最小天数获取 WeekFields 的实例。 |
| 的(区域设置) | 此方法获取适用于区域设置的 WeekFields 实例。 |
| toString() | 此方法获取此 WeekFields 实例的字符串表示形式。 |
| weekBasedYear() | 此方法返回一个字段，以基于该周字段访问基于周的年份。 |
| 每月周数() | 此方法返回一个字段，以基于此周字段访问一个月中的周。 |
| weekOfWeekBasedYear() | 此方法返回一个字段，以访问基于该周字段的一年中的周。 |
| 一年中的第几周() | 此方法返回一个字段，以基于此周字段访问一年中的周。 |

</figure>

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// WeekFields class

import java.time.DayOfWeek;
import java.time.LocalDate;
import java.time.temporal.TemporalField;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.MONDAY, 1);

        // creating separate temporal fields for each method

        // apply dayOfWeek()
        TemporalField dayOfWeek = weekFields.dayOfWeek();

        // apply weekBasedYear()
        TemporalField weekBasedYear
            = weekFields.weekBasedYear();

        // apply weekOfMonth()
        TemporalField weekOfMonth
            = weekFields.weekOfMonth();

        // apply weekOfWeekBasedYear()
        TemporalField weekOfWeekBasedYear
            = weekFields.weekOfWeekBasedYear();

        // create a LocalDate
        LocalDate day = LocalDate.of(2021, 03, 31);

        // get day of week for localdate
        int dow = day.get(dayOfWeek);

        // get week based year for localdate
        int wby = day.get(weekBasedYear);

        // get week of month for localdate
        int wom = day.get(weekOfMonth);

        // get week of week for localdate
        int wow = day.get(weekOfWeekBasedYear);

        // print results

        System.out.println("day of week for " + day + " :"
                           + dow);
        System.out.println("week based year for " + day
                           + " :" + wby);
        System.out.println("week of month for " + day + " :"
                           + wom);
        System.out.println("Week of week for " + day + " :"
                           + wow);
    }
}
```

**Output**

```
day of week for 2021-03-31 :3
week based year for 2021-03-31 :2021
week of month for 2021-03-31 :5
Week of week for 2021-03-31 :14

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// WeekFields class

import java.time.DayOfWeek;
import java.time.LocalDate;
import java.time.temporal.TemporalField;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.SUNDAY, 1);

        // creating separate temporal fields for each method

        // apply dayOfWeek()
        TemporalField dayOfWeek = weekFields.dayOfWeek();

        // apply weekBasedYear()
        TemporalField weekBasedYear
            = weekFields.weekBasedYear();

        // apply weekOfMonth()
        TemporalField weekOfMonth
            = weekFields.weekOfMonth();

        // apply weekOfWeekBasedYear()
        TemporalField weekOfWeekBasedYear
            = weekFields.weekOfWeekBasedYear();

        // create a LocalDate
        LocalDate day = LocalDate.of(2021, 12, 05);

        // get day of week for localdate
        int dow = day.get(dayOfWeek);

        // get week based year for localdate
        int wby = day.get(weekBasedYear);

        // get week of month for localdate
        int wom = day.get(weekOfMonth);

        // get week of week for localdate
        int wow = day.get(weekOfWeekBasedYear);

        // print results

        System.out.println("day of week for " + day + " :"
                           + dow);
        System.out.println("week based year for " + day
                           + " :" + wby);
        System.out.println("week of month for " + day + " :"
                           + wom);
        System.out.println("Week of week for " + day + " :"
                           + wow);
    }
}
```

**Output**

```
day of week for 2021-12-05 :1
week based year for 2021-12-05 :2021
week of month for 2021-12-05 :2
Week of week for 2021-12-05 :50

```