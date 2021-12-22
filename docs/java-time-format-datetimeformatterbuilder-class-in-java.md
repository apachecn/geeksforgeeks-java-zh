# java 中的 Java . time . format . datetime formatterbuilder 类

> 原文:[https://www . geesforgeks . org/Java-time-format-datetimeformatterbuilder-class-in-Java/](https://www.geeksforgeeks.org/java-time-format-datetimeformatterbuilder-class-in-java/)

**DateTimeFormatterBuilder 类**是一个用于创建日期时间格式化程序的构建器类。日期时间格式化程序用作打印和解析日期时间对象的格式化程序。DateTimeFormatterBuilder 允许创建一个 DateTimeFormatter。DateTimeFormatterBuilder 用于构造格式化程序，然后用于打印或解析。格式化程序是通过将特定字段或其他格式化程序附加到此生成器的实例中来构建的。如果我们想创建自己的 DateTimeFormatter 对象，那么 Java . time . format . datetime formatter builder 会有所帮助。所有日期时间格式化程序最终都是使用该生成器创建的。

**语法:**

```java
public final class DateTimeFormatterBuilder
extends Object
```

让我们先讨论这个类的构造函数，然后再深入讨论这个类的方法

<figure class="table">

| **施工方** | **描述** |
| --- | --- |
| DateTimeFormatterBuilder() | 构造生成器的新实例。 |

</figure>

**方法:**

让我们讨论一下这个类中的方法，它在这个类中声明如下:

```java
clone()
equals()
finalize()
getClass()
hashCode()
notify()
notifyAll()
toString()
wait() 
```

下面以表格形式按字母顺序描绘了它们，以及它们执行的如下操作:

<figure class="table">

| **方法** | 已执行的操作 |
| --- | --- |
| 追加(日期时间格式化程序格式化程序) | 将格式化程序的所有元素追加到生成器中。 |
| 附录年表() | 向格式化程序追加年表标识，如“国际标准化组织”或“泰国历史”。 |
| 附录时间码文字(TextStyle textStyle) | 将年表名称追加到格式化程序。 |
| 追加分数(临时字段，整数最小宽度，整数最大宽度，布尔十进制点) | 将日期时间字段的小数值追加到格式化程序中。 |
| appendInstant() | 使用 ISO-8601 将一个瞬间追加到格式化程序中，格式化三个一组的小数位数。 |
| append instant(int fractional digits) | 使用 ISO-8601 向格式化程序追加一个控制小数位数的瞬间。 |
| 附加文字(字符文字) | 向格式化程序追加一个字符文本。 |
| 附加文字(字符串文字) | 将字符串文字追加到格式化程序。 |
| 附录本地化(格式样式日期样式，格式样式时间样式) | 向格式化程序追加本地化的日期时间模式。 |
| appendlocalized offset(text style) | 将本地化区域偏移量(如“格林尼治时间+01:00”)追加到格式化程序。 |
| 追加偏移量(字符串模式，字符串编号设置文本) | 向格式化程序追加区域偏移量，如“+01:00”。 |
| appendOffsetId() | 向格式化程序追加区域偏移量，如“+01:00”。 |
| 附录可选(日期时间格式化程序格式化程序) | 向生成器追加一个格式化程序，该程序可以选择格式化/解析。 |
| 附加模式(字符串模式) | 将指定模式定义的元素追加到生成器中。 |
| 附录文本(临时字段) | 使用全文样式将日期时间字段的文本追加到格式化程序。 |
| 附加文本(临时字段，映射<long>文本查找)</long> | 使用指定的映射将日期时间字段的文本追加到格式化程序以提供文本。 |
| appendText(临时字段，TextStyle textStyle) | 将日期时间字段的文本追加到格式化程序。 |
| 附加值(临时字段) | 使用常规输出样式将日期时间字段的值追加到格式化程序。 |
| 附加值(临时字段，整数宽度) | 使用固定宽度、零填充的方法将日期时间字段的值追加到格式化程序。 |
| appendValue(临时字段，int minWidth，int maxWidth，SignStyle signStyle) | 将日期-时间字段的值追加到格式化程序，以提供对格式化的完全控制。 |
| appendValueReduced(临时字段，整数宽度，整数最大宽度，整数基本日期) | 将日期时间字段的缩减值追加到格式化程序。 |
| appendValueReduced(临时字段，整数宽度，整数最大宽度，整数基本值) | 将日期时间字段的缩减值追加到格式化程序。 |
| appendZoneId() | 向格式化程序追加时区标识，如“欧洲/巴黎”或“+02:00”。 |
| appendZoneOrOffsetId() | 使用最佳可用区域标识，将时区标识(如“欧洲/巴黎”或“+02:00”)追加到格式化程序。 |
| appendZoneRegionId() | 将时区区域标识(如“欧洲/巴黎”)追加到格式化程序，如果是区域偏移量，则拒绝该区域标识 |
| append zonetext(text style text style) | 向格式化程序追加时区名称，如“英国夏令时”。 |
| 附加区域文本(文本样式文本样式，设置<zoneid>首选区域)</zoneid> | 向格式化程序追加时区名称，如“英国夏令时”。 |
| getLocalizedDateTimePattern() | 获取区域设置和时间表的日期和时间样式的格式模式。 |
| optionalEnd() | 结束可选部分。 |
| optionalStart() | 标记可选部分的开始。 |
| padNext（int padWidth） | 使下一个添加的打印机/解析器使用空格填充到固定宽度。 |
| padNext（int padWidth， char padChar） | 使下一个添加的打印机/解析器填充到固定宽度。 |
| parseCaseInsensitive() | 将解析样式更改为对格式化程序的其余部分不区分大小写。 |
| parseCaseSensitive() | 将解析样式更改为对格式化程序的其余部分区分大小写。 |
| parseDefaulting() | 将字段的默认值追加到格式化程序中，以便在分析时使用。 |
| parseLenient() | 将解析样式更改为对格式化程序的其余部分宽松。 |
| parseStrict() | 将解析样式更改为对格式化程序的其余部分严格。 |
| toFormatter() | 通过使用默认区域设置创建 DateTimeFormatter 来完成此生成器。 |
| toFormatter(本地) | 通过使用指定的区域设置创建 DateTimeFormatter 来完成此生成器。 |

</figure>

现在让我们在干净的 java 程序的帮助下，通过调用这个类的一些方法来实现，以便通过实现它的方法来更好地理解这个类。

**实施:**

> 在 LocalDateTime 类中，根据传递给它的参数，有三种 now()方法。本地日期时间类的 [*now()方法*](https://www.geeksforgeeks.org/localdatetime-now-method-in-java-with-examples/) 用于从默认时区的系统时钟获取当前日期时间。该方法将基于****系统时钟和****默认时区返回本地日期时间，获取当前日期时间。********

********例 1********

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java Program to illustrate DateTimeFormatterBuilder class
// by invoking appendValue() Method of this class

// Importing required classes from respective packages
import java.io.*;
import java.lang.*;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.time.format.DateTimeFormatterBuilder;
import java.time.format.TextStyle;
import java.time.temporal.ChronoField;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of this class
        DateTimeFormatterBuilder builder
            = new DateTimeFormatterBuilder();

        // Now creating object of DateTimeFormatter class
        // over which appendValue() method is invoked
        DateTimeFormatter formatter
            = builder.appendLiteral("Day is:")
                  .appendValue(ChronoField.DAY_OF_MONTH)
                  .appendLiteral(", month is:")
                  .appendValue(ChronoField.MONTH_OF_YEAR)
                  .toFormatter();

        // Creating object of LocalDateTime class
        // invoking now() method over it
        LocalDateTime dateTime = LocalDateTime.now();

        String str = dateTime.format(formatter);

        // Print and display the day and month
        System.out.println(str);
    }
}**
```

******Output**

```java
Day is:7, month is:7
```**** 

******例 2******

******选项开始()和选项结束()方法******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java program to illustrate DateTimeFormatterBuilder
// Using optionalStart() and optionalEnd() Methods

// Importing required libraries
import java.io.*;
import java.lang.*;
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.time.format.DateTimeFormatterBuilder;
import java.time.temporal.ChronoField;

// Main class
public class GFG {

    // Main driver methods
    public static void main(String[] args)
    {

        // Creating an object of DateTimeFormatter class
        DateTimeFormatter parser
            = new DateTimeFormatterBuilder()
                  .appendPattern("[yyyy][yyyyMM][yyyyMMdd]")
                  .optionalStart()
                  .parseDefaulting(
                      ChronoField.MONTH_OF_YEAR, 1)
                  .parseDefaulting(ChronoField.DAY_OF_MONTH,
                                   1)
                  .optionalEnd()
                  .toFormatter();

        // Print and display statements

        // Execute if only year is given in parameter
        System.out.println(
            parser.parse("2021", LocalDate::from));

        // Execute if year and month is given
        System.out.println(
            parser.parse("202106", LocalDate::from));

        // Execute if year, month and date is given
        System.out.println(
            parser.parse("20210631", LocalDate::from));
    }
}**
```

******Output**

```java
2021-01-01
2021-06-01
2021-06-30
```**** 

******例 3******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java program to illustrate DateTimeFormatterBuilder class

// Importing required classes from respective packages
import java.io.*;
import java.lang.*;
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.time.format.DateTimeFormatterBuilder;
import java.time.format.TextStyle;
import java.time.temporal.ChronoField;
import java.util.Locale;

// Main class
// DateTimeFormatterBuilderExample
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creat
        LocalDate date = LocalDate.of(2021, 6, 30);

        // Creating object of DateTimeFormatter class to
        //

        // Object 1
        DateTimeFormatter formatter
            = DateTimeFormatter.ofPattern("dd/MM/yyyy");

        // Object 2
        DateTimeFormatter italianFormatter
            = DateTimeFormatter.ofPattern("d. MMMM yyyy",
                                          Locale.ITALIAN);

        // Print and display date in format XX-XX-XX
        System.out.println(
            date.format(DateTimeFormatter.ISO_LOCAL_DATE));

        // Print and display date in format XX/XX/XX
        System.out.println(date.format(formatter));

        // Print and display Italian date formatter
        System.out.println(date.format(italianFormatter));

        // Object 3
        DateTimeFormatter complexFormatter
            = new DateTimeFormatterBuilder()
                  .appendText(ChronoField.DAY_OF_MONTH)
                  .appendLiteral(". ")
                  .appendText(ChronoField.MONTH_OF_YEAR)
                  .appendLiteral(" ")
                  .appendText(ChronoField.YEAR)
                  .parseCaseInsensitive()
                  .toFormatter(Locale.US);

        // Print ad display US date formatter
        System.out.println(date.format(complexFormatter));
    }
}**
```

******Output**

```java
2021-06-30
30/06/2021
30\. giugno 2021
30\. June 2021
```****