# Java 程序以不同格式显示日历年的日期

> 原文:[https://www . geesforgeks . org/Java-程序-以不同格式显示日历年的日期/](https://www.geeksforgeeks.org/java-program-to-display-dates-of-a-calendar-year-in-different-format/)

因为不同的国家选择不同的格式。所以这里的目标只是打印不同年份的日历日期。全球通用的符号表示法是:

<figure class="table">

| 符号符号 | 描述 |
| --- | --- |
| y | 年 |
| M | 一年中的月份 |
| d | 每月的某一天 |
| E | 一周中的某一天 |

</figure>

**概念:**每当说到日期和时间，首要目标就是 [**日期类**](https://www.geeksforgeeks.org/date-class-java-examples/) **。**它是需要导入到我们程序中的。

[日期类](https://www.geeksforgeeks.org/date-class-java-examples/)在 JDK 1.0 版本的 java 中引入，但后来在 JDK 1.1 中通过引入[日历类](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/)进行了改进。它否决了大多数日历类，因为 6 个构造函数中有 4 个被标记为否决，并且其中的大多数方法都被标记为否决。这两个 JDK 现在已经过时了，因此被称为遗留应用编程接口。最后，2014 年在 JDK8 中引入了新的日期/时间 API。它包括 java.time 包，现在是*日期、时间、时刻*、*和持续时间的主要 API。*

<figure class="table">

| 班级 | 描述 |
| --- | --- |
| 时钟 | 使用时区提供当前即时、日期和时间的时钟 |
| 持续时间 | 基于时间的时间量，如“34.5 秒” |
| 瞬间 | 时间线上的一个瞬间点 |
| 局部日期 | 没有时间杂志的日期，如 2007 年 12 月 3 日 |
| LocalTime(本地时间) | 日历系统中没有时区的时间 |
| 蒙特达伊 | 日历系统中的月日 |
| 偏移时间 | 日历系统中偏离格林威治时间的时间 |
| 时期 | 日历系统中基于数据的时间量 |
| 年 | 日历系统中的一年 |
| ZonedDateTime | 日历中带有时区的日期 |
| ZoneOffset(区域偏移) | 从格力*到*的时区偏移 |

</figure>

**在 JDK 包装爪哇时间 8**

*在 java 中，有不同的方法可以获得当前的日期和时间。Java 没有内置的 Date 类，尽管我们可以导入 java.time 包来使用时间和日期 API。一些课程如下:*

*   *[**Java . time . local date**](https://www.geeksforgeeks.org/localdate-format-method-in-java/)–表示日期(年、月、日(yyyy-MM-dd))。*
*   *[**Java . time . local datetime**](https://www.geeksforgeeks.org/localdatetime-parse-method-in-java-with-examples/)–表示日期和时间(yyyy-MM-dd-HH-mm-ss-ns)。*
*   *[**Java . time . format . datetime formatter**](https://www.geeksforgeeks.org/localdate-format-method-in-java/)–用于显示和解析日期时间对象的格式化程序。*

> *当需要以不同的格式显示日期和时间时，使用 *ofPattern()* 方法来接受各种值。有许多格式可以在以后调用，可以混合和匹配字母来实现所需的模式。*

*这里将涉及 3 种格式:*

1.  *年-月-日*
2.  *日/月/YY*
3.  *dd MMM yyyy*

*下面是不同日期格式的 java 程序。*

***格式 1: yyyy-MM-dd***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```
*// Java Program to Display Dates in Different Format

// Importing Classes/Files
import java.io.*;
// Importing speccificaly Time Class and functionalities
import java.time.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create an object of LoacalDate type
        LocalDate date = LocalDate.now();
        // .now() method to tore the current date

        // Print current date
        System.out.println(date);
    }
}*
```

***输出:***

```
*2020-11-03*
```

***格式二:DD/MM/YY***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```
*// Java Program to Display Dates in Different Format

// Importing generic Classes/Files
import java.io.*;
// Importing specific Date and Time Classes/Files
import java.time.*;
import java.time.format.DateTimeFormatter;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create date time object and store current time in
        // default format yy-mm-dd
        LocalDateTime date = LocalDateTime.now();

        // Creating DateTimeFormatter object
        // to specify date format
        DateTimeFormatter myDateFormat
            = DateTimeFormatter.ofPattern("dd/MM/yyyy");

        // Change date into your format and store it in
        // string object
        String formattedDate = date.format(myDateFormat);

        // Print formatted date
        System.out.println(formattedDate);
    }
}*
```

***输出:***

```
* 03/11/2020*
```

***格式 3:日，日 MMM yyyy***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```
*// Java Program to Display Dates in Different Format

// Importing generic Classes/Files
import java.io.*;
// Importing Date and time specific Classes
import java.time.*;
import java.time.format.DateTimeFormatter;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create date time object and store current time in
        // default format yy-mm-dd
        LocalDateTime date = LocalDateTime.now();

        // Specify the date format
        // Note: more than 3 characters result in full name
        DateTimeFormatter myDateFormat
            = DateTimeFormatter.ofPattern(
                "EEEE, dd MMM yyyy");
        // e.g- MMM = Oct and MMMM = October

        // Change date into req format and store it in
        // string object
        String formattedDate = date.format(myDateFormat);

        // Printing formatted date
        System.out.println(formattedDate);
    }
}*
```

***输出:***

```
* Tuesday, 03 Nov 2020*
```