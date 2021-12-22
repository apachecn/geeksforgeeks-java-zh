# 显示日历年工作日名称的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-display-日历年工作日名称/](https://www.geeksforgeeks.org/java-program-to-display-name-of-the-weekdays-in-calendar-year/)

**概念**:在 java 中，当遇到暴力方法后的日期和时间问题时，人们应该永远记住 java 的[日期类](https://www.geeksforgeeks.org/date-class-java-examples/)，它不仅提供打印当前或即将到来的年、月、日、日期、时间、小时、分钟，甚至精确到秒。不仅可以显示这些参数，还可以格式化以不同的格式显示它们。这门课领先一步。

现在为了显示日历年中工作日的名称:

**接近:**

*   使用现有的日期格式类
*   使用暴力方法

**方法 1:使用** [**日期格式**](https://www.geeksforgeeks.org/dateformat-format-method-in-java-with-examples/) **类**

它用于在 java 中显示数据和时间以及操作日期和时间，除此之外，它还用于在 java 中跨时区格式化日期、时间、周、月、年相关数据。

> 注:纪元时间为 1970 年 1 月 1 日

为了从一个名为 java.utils 的包中导入这个类

**语法:**

```java
import java.util.Date ;
```

导入该类后，可以创建日期类的对象，以便打印当前日期和时间。现在为了打印默认的日期和时间只需调用打印命令使用 [*toString()*](https://www.geeksforgeeks.org/integer-tostring-in-java/) 方法获取当前的日期和时间。假设用户想要当前时间的特定日期、时间和月份:

**示例示例:**在继续显示工作日名称之前，先用简单的代码阐明日期类的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Display name of the weekdays in calendar
// year Sample code showing different data class parameters

// Importing Libraries
import java.util.Date;
import java.util.*;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of Date class- date
        Date date = new Date();

        // Printing date
        System.out.println(date.toString());
        System.out.println(date.getTime());

        // Remember to add 1 to it because this print
        // current month Jan is assigned 0
        System.out.println(date.getMonth() + 1);

        // Remember to add 1 to it because this print
        // epoch year 1970 is set as reference
        system.out.println(date.getYear() + 1900);

        // For week internally it starts with Monday=1
        System.out.println(date.getDay(date));
        // no ambiguity here in displaying week
    }
}
```

所以现在如果要打印不同格式的日期和时间定制日期、时间、工作日、年份等等这就是问题陈述的目的。

1.  将导入名为 text 的类
2.  然后使用一个名为- [SimpleDateFormat](https://www.geeksforgeeks.org/simpledateformat-equals-method-in-java-with-examples/) 的类
3.  此后，需要调用 format 方法

**语法:**

```java
import java.text.*;
```

**下面的 Java 代码说明了被调用的内置类的用法:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Importing generic Classes/Files
import java.io.*;

// Importing specific text class for formatting
//  week via inbuilt function getweek() of data class
import java.text.DateFormatSymbols;
// Dealing with week parameter of data class

class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Inbuilt function to invoke weekdays by creating
        // an object of DateFormatSymbols
        String[] week_days
            = new DateFormatSymbols().getWeekdays();

        // Computing length to get end bound
        // for iteration
        int length = week_days.length;

        // Loop is started with 2 because 0th day is
        // saturday and 1st day is sunday
        for (int d = 2; d < (length - 1); d++) {

            // Iterating over the string array of weekdays
            // to get respective names
            String day = week_days[d];

            // Printing ith index weekday
            System.out.println((d - 1) + "th weekday - "
                               + day);
        }
    }
}
```

**Output**

```java
1th weekday - Monday
2th weekday - Tuesday
3th weekday - Wednesday
4th weekday - Thursday
5th weekday - Friday
```

[DateFormatSymbols](https://www.geeksforgeeks.org/dateformatsymbols-getweekdays-method-in-java-with-examples/) 是 Java 中的一个内置类，公开可用，用于组合各种日期时间格式数据实体，如月份名称、工作日和时区关联数据。简单日期格式使用日期格式符号来封装捕获的信息。这个类支持一个内置的方法 getWeekdays()，用于检索日历中工作日的名称。所有日期都以字符串格式返回。该方法在 Java 中具有以下语法:

```java
String[] getWeekdays() 
```

*   该方法不接受任何参数或参数。
*   它以字符串数组的形式返回日历工作日的名称。

**方法 2:蛮力**

一个日历中有五个工作日，可以以字符串数组的形式维护，并模拟一个 for 或 while 循环迭代包含工作日的数组或一个简单的开关情况。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Importing generic Classes/Files
import java.io.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a list of weekdays
        String[] weekdays
            = { "Monday", "Tuesday", "Wednesday",
                "Thursday", "Friday" };

        // Iterating 5 times only
        // since there are 5 weekdays
        for (int d = 1; d < 6; d++) {

            // Message printing weekdays in calendar year
            System.out.println(d + "th weekday - "
                               + weekdays[d - 1]);
        }
    }
}
```

**Output**

```java
1th weekday - Monday
2th weekday - Tuesday
3th weekday - Wednesday
4th weekday - Thursday
5th weekday - Friday
```