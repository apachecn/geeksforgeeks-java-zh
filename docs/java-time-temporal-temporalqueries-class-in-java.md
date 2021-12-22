# java 中的 java.time.temporal 查询类

> 原文:[https://www . geesforgeks . org/Java-time-temporal-temporal query-class-in-Java/](https://www.geeksforgeeks.org/java-time-temporal-temporalqueries-class-in-java/)

**时态查询**类提供了查询时态对象的常见实现。实现定义了查询的逻辑。查询是从时态对象中检索信息的关键工具。例如，查询检查日期是否在闰年 2 月 29 日之前，或者确定时间是否在营业时间之间。

**有两种使用临时查询的等效方式:**

**1。**直接在该界面调用方法:

```
 temporal = thisQuery.queryFrom(temporal);
```

**2。**使用临时查询:

```
temporal = temporal.query(thisQuery);
```

**类申报:**

> 公共最终类临时查询扩展了对象

**临时查询类从 java.lang.Object 类继承了以下方法:**

*   克隆()
*   等于()
*   最终确定()
*   getClass()
*   hashCode()
*   通知()
*   notifyAll()
*   toString()
*   等待()

**临时查询类的方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 年表() | 此方法返回对年表的查询。 |
| localDate() | 此方法返回对 LocalDate 的查询，如果找不到，则返回 null。 |
| localTime() | 此方法返回 LocalTime 的查询，如果找不到，则返回 null。 |
| 偏移量() | 此方法返回 ZoneOffset 的查询，如果找不到，则返回 null。 |
| 精度() | 此方法返回对支持的最小单位的查询。 |
| 区域() | 该方法返回对区域标识的宽松查询，返回到区域偏移量。 |
| zoneId() | 该方法返回对区域标识的宽松查询，返回到区域偏移量。 |

</figure>

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// TemporalQueries Class
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;
import java.time.Year;
import java.time.YearMonth;
import java.time.temporal.TemporalQueries;
import java.time.temporal.TemporalQuery;
import java.time.temporal.TemporalUnit;
public class GFG {

    public static void main(String[] args)
    {

        // creating a query to obtainsmallest supported unit
        // of a temporal
        TemporalQuery<TemporalUnit> precision
            = TemporalQueries.precision();

        System.out.println("TemporalQueries precision: ");

        // print smallest precision of local date
        System.out.println(
            LocalDate.now().query(precision));

        // print smallest precision of local time
        System.out.println(
            LocalTime.now().query(precision));

        // print smallest precision of local date-time
        System.out.println(
            LocalDateTime.now().query(precision));

        // print smallest precision of year-month
        System.out.println(
            YearMonth.now().query(precision));

        // print smallest precision of year
        System.out.println(Year.now().query(precision));
    }
}
```

**Output**

```
TemporalQueries precision: 
Days
Nanos
Nanos
Months
Years
```