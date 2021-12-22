# Java 程序以短格式显示日历年的月份名称

> 原文:[https://www . geesforgeks . org/Java-program-to-display-月份名称-日历-年份-简称/](https://www.geeksforgeeks.org/java-program-to-display-name-of-months-of-calendar-year-in-short-format/)

我们知道，在一个日历年中，总共有 12 个月。为了将月份的名称转换成更短的格式，基本上有两种方法，即我们可以使用日期格式符号类或简单日期格式类。这些类有用于将月份名称转换为较短格式的方法，例如，如果月份名称是十月，那么在较短格式中，它将表示为十月。

[DateFormatSymbols](https://www.geeksforgeeks.org/dateformatsymbols-getshortmonths-method-in-java-with-examples/) 类和 [SimpleDateFormat](https://www.geeksforgeeks.org/java-simpledateformat-set-1/) 类的主要区别在于，DateFormatSymbols 类登记日历年的所有月份，而 SimpleDateFormat 类登记该月的特定日期以及当前的月份和年份。

下面讨论了将日历年中的月份名称转换为较短格式的方法:

*   使用日期格式符号类
*   使用简单日期格式类

**示例 1:** 使用日期格式符号类以较短的格式显示月份

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert the names of the months into the
// shorter format using DateFormatSymbols class

import java.text.DateFormatSymbols;
import java.text.SimpleDateFormat;

public class GFG {
    public static void main(String[] args)
    {
        // making the object of the DateFormatSymbols class
        DateFormatSymbols dateFormatSymbolsobject = new DateFormatSymbols();

        // calling the method of the DateFormatSymbols class
        String[] shortFormatMonthsNames = dateFormatSymbolsobject.getShortMonths();

        for (int i = 0;i < (shortFormatMonthsNames.length - 1); i++) {

            // getting the month name  from particular index
            String shortMonthName = shortFormatMonthsNames[i];

            System.out.println("Name of Month In Shorter Format "
                + shortMonthName);
        }
    }
}
```

**Output**

```java
Name of Month In Shorter Format Jan
Name of Month In Shorter Format Feb
Name of Month In Shorter Format Mar
Name of Month In Shorter Format Apr
Name of Month In Shorter Format May
Name of Month In Shorter Format Jun
Name of Month In Shorter Format Jul
Name of Month In Shorter Format Aug
Name of Month In Shorter Format Sep
Name of Month In Shorter Format Oct
Name of Month In Shorter Format Nov
Name of Month In Shorter Format Dec
```

**示例 2:** 使用 SimpleDateFormat 类以较短的格式显示月份

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to display the name of the month in shorter
// format using SimpleDateFormat class

import java.text.Format;
import java.text.SimpleDateFormat;
import java.util.Calendar;
import java.util.Date;
import java.util.Locale;

public class GFG {
    public static void main(String[] argv) throws Exception
    {
        // The format of the date which we want to display
        String dateFormat = "dd-MMM-yyyy";

        // getting the date using getTime() method of the
        // Calendar class
        Date d = Calendar.getInstance().getTime();

        // getting the date in the form of dateFormat String
        // that we have mentioned above we have mentioned
        // Locale.English explicitly since,if we write
        // Locale.FRENCH,then we would have get the date in
        // some other notation
        SimpleDateFormat sdf = new SimpleDateFormat(dateFormat, Locale.ENGLISH);

        // printing the date with the month name in the
        // shorter format
        System.out.println(sdf.format(d));
    }
}
```

**Output**

```java
01-Feb-2021
```