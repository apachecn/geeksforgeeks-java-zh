# java 中的 java.time.ZonedDateTime 类

> 原文:[https://www . geesforgeks . org/Java-time-zoneddatetime-in-Java 类/](https://www.geeksforgeeks.org/java-time-zoneddatetime-class-in-java/)

ZonedDateTime 是一个不可变的对象，代表日期时间和时区。此类存储所有日期和时间字段。这个类存储精确到纳秒的时间和一个时区，用一个区域偏移量来处理本地日期时间。例如，值“2011 年 10 月 2 日亚洲/加尔各答时区 14:45.30.123456789 +05:30”可以存储在 ZonedDateTime 中。此类还用于将本地日期时间的本地时间线转换为即时的即时时间线。

**类别申报:**

```
public final class ZonedDateTime
extends Object
implements Temporal, ChronoZonedDateTime<LocalDate>, Serializable
```

**方法:**

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [等于(对象对象)](https://www.geeksforgeeks.org/zoneddatetime-equals-method-in-java-with-examples/) | 此方法检查此日期时间是否等于另一个日期时间。 |
| [格式(DateTimeFormatter 格式化程序)](https://www.geeksforgeeks.org/zoneddatetime-format-method-in-java-with-examples/) | 此方法使用指定的格式化程序格式化此日期时间。 |
| [从(临时处理器临时)](https://www.geeksforgeeks.org/zoneddatetime-form-method-in-java-with-examples/) | 此方法从时态对象中获取 ZonedDateTime 的实例。 |
| [获取(临时字段)](https://www.geeksforgeeks.org/zoneddatetime-get-method-in-java-with-examples/)

 | 此方法从该日期时间获取指定字段的值作为 int。 |
| [getDayOfMonth（）](https://www.geeksforgeeks.org/zoneddatetime-getdayofmonth-method-in-java-with-examples/) | 此方法获取月中的某一天字段。 |
| [getDayOfWeek（）](https://www.geeksforgeeks.org/zoneddatetime-getdayofweek-method-in-java-with-examples/) | 此方法获取星期几字段，这是一个枚举 DayOfWeek。 |
| [getDayOfYear（）](https://www.geeksforgeeks.org/zoneddatetime-getdayofyear-method-in-java-with-examples/) | 此方法获取年中的某一天字段。 |
| [getHour()](https://www.geeksforgeeks.org/zoneddatetime-gethour-method-in-java-with-examples/) | 此方法获取一天中的小时字段。 |
| [getLong(临时字段)](https://www.geeksforgeeks.org/zoneddatetime-getlong-method-in-java-with-examples/)

 | 此方法从该日期时间中获取指定字段的值作为长整型。 |
| [getMinute()](https://www.geeksforgeeks.org/zoneddatetime-getminute-method-in-java-with-examples/) | 此方法获取分钟/小时字段。 |
| [getMonth（）](https://www.geeksforgeeks.org/zoneddatetime-getmonth-method-in-java-with-examples/) | 此方法使用月份枚举获取年度月份字段。 |
| [getMonthValue（）](https://www.geeksforgeeks.org/zoneddatetime-getmonthvalue-method-in-java-with-examples/) | 此方法获取从 1 到 12 的年月字段。 |
| get nano() | 这种方法可以得到纳米秒的磁场。 |
| getOffset() | 此方法获取区域偏移量，如“+01:00”。 |
| get econd() | 此方法获取分钟秒字段。 |
| [年数()](https://www.geeksforgeeks.org/zoneddatetime-getyear-method-in-java-with-examples/) | 此方法获取年份字段。 |
| get zone() | 此方法获取时区，如“欧洲/巴黎”。 |
| [hashCode()](https://www.geeksforgeeks.org/zoneddatetime-hashcode-method-in-java-with-examples/) | 此日期时间的哈希代码。 |
| [发布支持(临时字段)](https://www.geeksforgeeks.org/zoneddatetime-issupported-method-in-java-with-examples/)

 | 此方法检查指定的字段是否受支持。 |
| [发布支持(临时单位)](https://www.geeksforgeeks.org/zoneddatetime-issupported-method-in-java-with-examples/) | 此方法检查指定的单元是否受支持。 |
| [减(长 amountToSubtract，临时单位)](https://www.geeksforgeeks.org/zoneddatetime-minus-method-in-java-with-examples/) | 此方法返回减去指定金额后的日期时间副本。 |
| [减(临时数量到子管道)](https://www.geeksforgeeks.org/zoneddatetime-minus-method-in-java-with-examples/) | 此方法返回减去指定金额后的日期时间副本。 |
| [不稳定日(长日)](https://www.geeksforgeeks.org/zoneddatetime-minusdays-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的天数。 |
| [小时(长时间)](https://www.geeksforgeeks.org/zoneddatetime-minushours-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的小时数。 |
| [分钟(长分钟)](https://www.geeksforgeeks.org/zoneddatetime-minusminutes-method-in-java-with-examples/) | 此方法返回该区域的副本，减去指定的分钟数。 |
| [不稳定月份(长月份)](https://www.geeksforgeeks.org/zoneddatetime-minusmonths-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的月数。 |
| [小写(长纳秒)](https://www.geeksforgeeks.org/zoneddatetime-minusnanos-method-in-java-with-examples/) | 此方法返回此 ZonedDateTime 的副本，并减去指定的纳秒数。 |
| [不稳定秒(长秒)](https://www.geeksforgeeks.org/zoneddatetime-minusseconds-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的秒数。 |
| [不稳定周(长周)](https://www.geeksforgeeks.org/zoneddatetime-minusweeks-method-in-java-with-examples/)

 | 此方法返回该区域的副本，减去指定的周数。 |
| [负年(长年)](https://www.geeksforgeeks.org/zoneddatetime-minusyears-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的年数。 |
| [现在()](https://www.geeksforgeeks.org/zoneddatetime-now-method-in-java-with-examples/) | 此方法从默认时区的系统时钟获取当前日期时间。 |
| [现在(时钟)](https://www.geeksforgeeks.org/zoneddatetime-now-method-in-java-with-examples/) | 此方法从指定的时钟获取当前日期时间。 |
| [现在(ZoneId zone)](https://www.geeksforgeeks.org/zoneddatetime-now-method-in-java-with-examples/) | 此方法从指定时区的系统时钟获取当前日期时间。 |
| [的(整年、整月、整日、整小时、整分钟、整秒、整纳秒、区域标识区)](https://www.geeksforgeeks.org/zoneddatetime-of-method-in-java-with-examples/) | 此方法从年、月、日、小时、分钟、秒、纳秒和时区获取 ZonedDateTime 的实例。 |
| [of(LocalDate，LocalTime，ZoneId zone)](https://www.geeksforgeeks.org/zoneddatetime-of-method-in-java-with-examples/) | 此方法从本地日期和时间获取 ZonedDateTime 的实例。 |
| [of(localdatetime local datetime，ZoneId zone)](https://www.geeksforgeeks.org/zoneddatetime-of-method-in-java-with-examples/) | 此方法从本地日期时间获取 ZonedDateTime 的实例。 |
| [办公常数(即时、分区)](https://www.geeksforgeeks.org/zoneddatetime-ofinstant-class-in-java-with-examples/) | 此方法从即时获取 ZonedDateTime 的实例。 |
| [办公常数(LocalDateTime，ZoneOffset，ZoneId zone)](https://www.geeksforgeeks.org/zoneddatetime-ofinstant-class-in-java-with-examples/) | 此方法从通过组合本地日期时间和偏移量形成的瞬间获取 ZonedDateTime 的实例。 |
| [ofLocal(LocalDateTime，ZoneId zone，ZoneOffset preferredOffset)](https://www.geeksforgeeks.org/zoneddatetime-oflocal-method-in-java-with-examples/)

 | 如果可能，此方法使用首选偏移量从本地日期时间获取 ZonedDateTime 的实例。 |
| [of sett(localdatetime local datetime，ZoneOffset，ZoneId zone)](https://www.geeksforgeeks.org/zoneddatetime-ofstrict-method-in-java-with-examples/) | 此方法获取一个严格验证本地日期时间、偏移量和区域标识组合的区域数据时间实例。 |
| 剖析(CharSequence text) | 此方法从文本字符串(如 2007-12-03t 10:15:30+01:00[欧洲/巴黎])中获取 ZonedDateTime 的实例 |
| [解析(字符序列文本，日期时间格式化程序格式化程序)](https://www.geeksforgeeks.org/zoneddatetime-parse-method-in-java-with-examples/) | 此方法使用特定的格式化程序从文本字符串中获取 ZonedDateTime 的实例。 |
| [加(长火腿，临时单位)](https://www.geeksforgeeks.org/zoneddatetime-plus-method-in-java-with-examples/) | 此方法返回添加了指定金额的日期时间的副本。 |
| [plus(amounttoadd 暂调)](https://www.geeksforgeeks.org/zoneddatetime-plus-method-in-java-with-examples/) | 此方法返回添加了指定金额的日期时间的副本。 |
| [plusDays(长时间)](https://www.geeksforgeeks.org/zoneddatetime-plusdays-method-in-java-with-examples/) | 此方法返回添加了指定天数的此 ZonedDateTime 的副本。 |
| [plus shour(长时间)](https://www.geeksforgeeks.org/zoneddatetime-plushours-method-in-java-with-examples/) | 此方法返回添加了指定小时数的此 ZonedDateTime 的副本。 |
| 多分钟(长分钟) | 此方法返回添加了指定分钟数的此 ZonedDateTime 的副本。 |
| [多月(长月)](https://www.geeksforgeeks.org/zoneddatetime-plusmonths-method-in-java-with-examples/) | 此方法返回添加了指定月数的此 ZonedDateTime 的副本。 |
| 加纳秒(长纳秒)

 | 此方法返回添加了指定纳秒数的此 ZonedDateTime 的副本。 |
| [plusSeconds(长秒)](https://www.geeksforgeeks.org/zoneddatetime-plusseconds-method-in-java-with-examples/) | 此方法返回添加了指定秒数的此 ZonedDateTime 的副本。 |
| [plusWeeks(长周)](https://www.geeksforgeeks.org/zoneddatetime-plusweeks-method-in-java-with-examples/) | 此方法返回添加了指定周数的此 ZonedDateTime 的副本。 |
| [plusYears(长年份)](https://www.geeksforgeeks.org/zoneddatetime-plusyears-method-in-java-with-examples/) | 此方法返回添加了指定年数的此 ZonedDateTime 的副本。 |
| [查询(临时查询< R >查询)](https://www.geeksforgeeks.org/zoneddatetime-query-method-in-java-with-examples/) | 此方法使用指定的查询来查询此日期时间。 |
| [范围(临时字段)](https://www.geeksforgeeks.org/zoneddatetime-range-method-in-java-with-examples/) | 此方法获取指定字段的有效值范围。 |
| [【tolocaldate()](https://www.geeksforgeeks.org/zoneddatetime-tolocaldate-method-in-java-with-examples/) | 此方法获取此日期时间的 LocalDate 部分。 |
| [toLocalDateTime()](https://www.geeksforgeeks.org/zoneddatetime-tolocaldatetime-method-in-java-with-examples/) | 此方法获取此日期时间的本地日期时间部分。 |
| [【tolocaltime()](https://www.geeksforgeeks.org/zoneddatetime-tolocaltime-method-in-java-with-examples/) | 这个方法获取这个日期时间的 LocalTime 部分。 |
| [toOffsetDateTime()](https://www.geeksforgeeks.org/zoneddatetime-tooffsetdatetime-method-in-java-with-examples/) | 此方法将此日期时间转换为 OffsetDateTime。 |
| [toString()](https://www.geeksforgeeks.org/zoneddatetime-tostring-method-in-java-with-examples/) | 此方法将此日期时间输出为字符串，例如 2007-12-03t 10:15:30+01:00[欧洲/巴黎]。 |
| [截断至(时间单位)](https://www.geeksforgeeks.org/zoneddatetime-truncatedto-method-in-java-with-examples/) | 此方法返回时间被截断的该区域的副本。 |
| [直到(临时结束，临时单位)](https://www.geeksforgeeks.org/zoneddatetime-until-method-in-java-with-examples/) | 此方法根据指定的单位计算到另一个日期时间的时间量。 |
| [带(临时调节器)](https://www.geeksforgeeks.org/zoneddatetime-with-method-in-java-with-examples/) | 此方法返回此日期时间的调整副本。 |
| [带(临时字段，长新值)](https://www.geeksforgeeks.org/zoneddatetime-with-method-in-java-with-examples/) | 此方法返回此日期时间的副本，并将指定字段设置为新值。 |
| [与月日（月中日）](https://www.geeksforgeeks.org/zoneddatetime-withdayofmonth-method-in-java-with-examples/)

 | 此方法返回更改了月中某一天的 ZonedDateTime 的副本。 |
| [带 DayOfYear(int dayOfYear)](https://www.geeksforgeeks.org/zoneddatetime-withdayofyear-method-in-java-with-examples/) | 此方法返回一个更改了日期的 ZonedDateTime 副本。 |
| [with Arrieroffsetatoverlap()](https://www.geeksforgeeks.org/zoneddatetime-withearlieroffsetatoverlap-method-in-java-with-examples/) | 此方法返回此日期时间的副本，将区域偏移更改为本地时间线重叠处两个有效偏移中较早的一个。 |
| [withFixedOffsetZone()](https://www.geeksforgeeks.org/zoneddatetime-withfixedoffsetzone-method-in-java-with-examples/) | 此方法返回此日期时间的副本，并将区域标识设置为偏移量。 |
| [小时数](https://www.geeksforgeeks.org/zoneddatetime-withhour-method-in-java-with-examples/) | 此方法返回一个更改了一天中某个小时的 ZonedDateTime 的副本。 |
| [白喉胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状胶状](https://www.geeksforgeeks.org/zoneddatetime-withlateroffsetatoverlap-method-in-java-with-examples/) | 此方法返回此日期时间的副本，将区域偏移更改为本地时间线重叠处两个有效偏移中的较晚者。 |
| [带分钟(int minute)](https://www.geeksforgeeks.org/zoneddatetime-withminute-method-in-java-with-examples/) | 此方法返回此 ZonedDateTime 的副本，其中更改了分钟/小时。 |
| [withMonth(int month)](https://www.geeksforgeeks.org/zoneddatetime-withmonth-method-in-java-with-examples/) | 此方法返回此 ZonedDateTime 的副本，其中更改了年月日。 |
| [撤回(int nanofsecond)](https://www.geeksforgeeks.org/zoneddatetime-withnano-method-in-java-with-examples/) | 此方法返回一个更改了纳米秒的 ZonedDateTime 的副本。 |
| [带秒(整数秒)](https://www.geeksforgeeks.org/zoneddatetime-withsecond-method-in-java-with-examples/) | 此方法返回此 ZonedDateTime 的副本，更改了分钟的秒数。 |
| [带年份(整年)](https://www.geeksforgeeks.org/zoneddatetime-withyear-method-in-java-with-examples/) | 此方法返回一个更改了年份的 ZonedDateTime 的副本。 |
| [withzonesame instant(zoneid zone)](https://www.geeksforgeeks.org/zoneddatetime-withzonesameinstant-method-in-java-with-examples/) | 此方法返回具有不同时区的此日期时间的副本，保留即时消息。 |
| [withzonesame local(zoneid zone)](https://www.geeksforgeeks.org/zoneddatetime-withzonesamelocal-method-in-java-with-examples/) | 此方法返回具有不同时区的此日期时间的副本，如果可能，保留本地日期时间。 |

</figure>

parse()方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to create a new
// ZonedDateTime using parse() method
import java.time.ZonedDateTime;

public class GFG {

    public static void main(String[] args)
    {
        String text
            = "2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]";
        // creating a new ZonedDateTime object
        ZonedDateTime zone = ZonedDateTime.parse(text);
        System.out.println(zone);
    }
}
```

**Output**

```
2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]

```

getZone()方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to illustrate working of getZone() method
import java.time.ZonedDateTime;

public class GFG {

    public static void main(String[] args)
    {
        String text
            = "2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]";

        // Creating a new ZonedDateTime object
        ZonedDateTime zone = ZonedDateTime.parse(text);

        // printing the zone of this zonedDateTime object
        System.out.println(zone.getZone());
    }
}
```

**Output**

```
Asia/Kolkata

```

加号()和减号()方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to illustrate working
// of plus() and minus() method
import java.time.Period;
import java.time.ZonedDateTime;

public class GFG {

    public static void main(String[] args)
    {
        String text
            = "2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]";

        // Creating a new ZonedDateTime object
        ZonedDateTime zone = ZonedDateTime.parse(text);

        // printing original value of
        // this ZonedDateTime object
        System.out.println(zone);
        // printing value of this ZonedDateTime
        // object after substracing two months
        System.out.println(zone.minus(Period.ofMonths(2)));
        // printing value of this ZonedDateTime
        // object after adding two months
        System.out.println(zone.plus(Period.ofMonths(2)));
    }
}
```

**Output**

```
2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]
2011-08-02T14:45:30.123456789+05:30[Asia/Kolkata]
2011-12-02T14:45:30.123456789+05:30[Asia/Kolkata]

```

()方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate working of of() method
import java.time.LocalDate;
import java.time.LocalTime;
import java.time.ZoneId;
import java.time.ZonedDateTime;

public class GFG {

    public static void main(String[] args)
    {
        // getting current date
        LocalDate date = LocalDate.now();

        // getting current time
        LocalTime time = LocalTime.now();

        // getting system default zone id
        ZoneId zoneId = ZoneId.systemDefault();

        // creating a new ZonedDateTime object
        ZonedDateTime zonedatetime
            = ZonedDateTime.of(date, time, zoneId);
        System.out.println(zonedatetime);
    }
}
```

**Output**

```
2021-03-20T17:09:56.241560Z[Etc/UTC]

```