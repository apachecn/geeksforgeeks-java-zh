# java 中的 java.time.LocalDate 类

> 原文:[https://www . geesforgeks . org/Java-time-local date-class-in-Java/](https://www.geeksforgeeks.org/java-time-localdate-class-in-java/)

[Java](https://www.geeksforgeeks.org/java/) 是目前最流行的编程语言，也是应用最广泛的编程语言。Java 应用于各种应用，如移动应用、桌面应用、网络应用。在这个 Java 中 [java.time.LocalDate](https://www.geeksforgeeks.org/localdate-now-method-in-java-with-examples/) 类被导入，表示显示当前日期。

**java.time** :是用来和当前日期时间 API 一起工作的包。

**级:**

<figure class="table">

| 班级 | 描述 |
| --- | --- |
| 局部日期 | 这是一个表示日期的类。 |
| 日期时间格式化程序 | 它是一个用于格式化和解析日期和时间的类。 |

</figure>

**方法:**

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| 调整(暂时的) | 此方法将指定的时态对象调整为与此对象具有相同的日期。 |
| atStartOfDay() | 此方法将此日期与午夜时间相结合，在此日期开始时创建一个本地日期时间。 |
| at tartofday(zoneid zone) | 此方法根据时区中的规则，从最早有效时间的该日期返回分区日期时间。 |
| 时间(整小时整分钟) | 此方法将此日期和时间结合起来创建一个本地日期时间。 |
| 时间(整数小时，整数分钟，整数秒) | 此方法将此日期和时间结合起来创建一个本地日期时间。 |
| 比较时间(其他时间) | 此方法将此日期与另一个日期进行比较。 |
| 等于(对象对象) | 此方法检查此日期是否等于另一个日期。 |
| 格式(日期格式器格式器) | 此方法使用指定的格式化程序格式化此日期。 |
| 来自(临时过程或临时) | 此方法从时态对象中获取 LocalDate 的实例。 |
| get(临时字段) | 此方法从该日期开始以 int 形式获取指定字段的值。 |
| get 年表() | 此方法获取此日期的年表，即 ISO 日历系统。 |
| getDayOfMonth() | 此方法获取月中的某一天字段。 |
| getDayOfWeek() | 此方法获取星期几字段，这是一个枚举 DayOfWeek。 |
| getDayOfYear() | 此方法获取年中的某一天字段。 |
| getEra() | 此方法获取在此日期适用的纪元。 |
| getLong(临时字段) | 此方法从该日期获取指定字段的值作为长整型。 |
| getMonth（） | 此方法使用月份枚举获取年度月份字段。 |
| getMonthValue() | 此方法获取从 1 到 12 的年月字段。 |
| getYear（） | 此方法获取年份字段。 |
| hashCode() | 此日期的哈希代码。 |
| isAfter(其他时间位置日期) | 此方法检查此日期是否在指定日期之后。 |
| isBefore(其他时间位置日期) | 此方法检查该日期是否在指定日期之前。 |
| isensequal(chrolcaldate other) | 此方法检查该日期是否等于指定日期。 |
| isleapyear() | 根据国际标准化组织日历系统规则，此方法检查年份是否为闰年。 |
| 问题支持(临时字段) | 此方法检查指定的字段是否受支持。 |
| 月长度() | 此方法返回由该日期表示的月份长度。 |
| 一年的长度() | 此方法返回由该日期表示的年份长度。 |
| 现在() | 这是一个用于返回 LocalDateTime 类实例的方法。 |
| 的模式（） | 这是一个与 DateTimeFormatter 一起使用的方法，用于格式化和解析日期和时间。它接受所有类型或种类的值，以不同的格式显示。 |
| 查询(临时查询<r>查询)</r> | 此方法使用指定的查询来查询此日期。 |
| 范围(临时字段) | 此方法获取指定字段的有效值范围。 |
| toEpochDay() | 此方法将此日期转换为纪元日。 |
| withDayOfMonth（int dayOfMonth） | 此方法返回一份更改了月日的本地日期。 |
| 一年中的某一天 | 此方法返回一份更改了日期的本地日期的副本。 |
| 带月(整数月) | 此方法返回一个本地日期的副本，其中更改了年月日。 |
| 带年份(整年) | 此方法返回一个更改了年份的本地日期的副本。 |

</figure>

**接近**

1.  用 java.time 包导入 java.time.LocalDateTime 和 Java . time . format . datetime formatter 等类。
2.  请使用 LocalDateTime.now()和 now()方法。
3.  使用 DateTimeFormatter.ofPattern 对当前日期进行排序。
4.  显示变量中存储的日期。

下面是问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// import package used to work with current date and time
// api.
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class GFG {

    public static void main(String[] args)
    {
        // now() is a method to return the
        // instance of LocalDateTime class.
        LocalDateTime localDate = LocalDateTime.now();
        // DateTimeFormatter class used to format and
        // parse date and time. ofPattern() is a method
        // used with DateTimeFormatter to format and
        // parse date and time.
        DateTimeFormatter dateformatter
            = DateTimeFormatter.ofPattern("MM dd, YYYY");
        // display the date
        System.out.println(dateformatter.format(localDate));
    }
}
```

**Output**

```java
03 16, 2021

```

**爪哇**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class GFG {

    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt1 = LocalDate.parse("2021-01-07");
        LocalDate result = dt1.withDayOfYear(01);

        // Prints the date with year
        System.out.println("The date with day of year is: "
                           + result);
    }
}
```

**Output**

```java
The date with day of year is: 2021-01-01

```