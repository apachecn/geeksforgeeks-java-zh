# 显示当前小时和当前分钟的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到显示-当前小时和当前分钟/](https://www.geeksforgeeks.org/java-program-to-display-current-hour-and-current-minute/)

Date 和 Calendar 的区别在于，Date 类在特定时刻运行，Calendar 在两个日期之间运行。日历类为您提供了在特定时间点和一组日历字段(如小时、年、月、月中的某一天)之间进行转换的可能性。对日历字段的操作，例如获取组织成立的回溯日期或生日。

**日历类**

它用于在 java 中显示日期和时间以及操作日期和时间，除此之外，它还用于在 java 中格式化跨时区关联数据的日期和时间类。所以为了从一个名为“ [*的包中导入这个类*](https://www.geeksforgeeks.org/java-util-package-java/) ”。导入该类后，可以创建日期类的对象，以便打印当前日期和时间。现在为了打印默认的日期和时间只需调用打印命令使用 [*toString()*](https://www.geeksforgeeks.org/integer-tostring-in-java/) 方法获取当前的日期和时间。

[*Java . util . calendar . get()*](https://www.geeksforgeeks.org/calendar-get-method-in-java/)方法是 **java.util.Calendar** 类的一个方法。Calendar 类提供了一些在包外实现具体日历系统的方法。日历字段的一些示例有:年、日、月、周、年、年、分、秒、小时、上午、下午、月、月、月、日。

**语法:**

```
public int get(int field)

```

这里，**字段**代表给定的日历
字段，函数返回
给定字段的值。

**接近:**

1.  使用 [**日历类**](https://www.geeksforgeeks.org/calendar-get-method-in-java/) 搭配 [**格式说明符**](https://www.geeksforgeeks.org/format-specifiers-in-java/)
2.  使用 [**日历类**](https://www.geeksforgeeks.org/calendar-get-method-in-java/) 不带 [**格式说明符**](https://www.geeksforgeeks.org/format-specifiers-in-java/)

**方法 1:** **使用带有** [**格式说明符的日历类**](https://www.geeksforgeeks.org/format-specifiers-in-java/)

方法是 java.util.Calendar 类的一个方法。Calendar 类提供了一些在包外实现具体日历系统的方法。格式说明符以百分比字符(%)开头，以表示数据类型(int、float 等)的“类型字符”结尾。)将以表示数据的基本方式(十进制、十六进制等)进行转换。)

<figure class="table">

| **说明符** | **转换已应用** |
| --- | --- |
| %% | 插入%符号 |
| %t %T | 时间和日期 |
| %tM | 分钟 |

</figure>

**实现:**下面是使用上述格式说明符的程序实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Display
// current hour and minute

// Importing java Date class libraries
import java.util.Calendar;
import java.util.Formatter;

class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Create Formatter class object
        Formatter formate = new Formatter();

        // Creating a calendar
        Calendar gfg_calender = Calendar.getInstance();

        // Displaying hour using Format clas using  format
        // specifiers
        // '%tl' for hours and '%tM' for minutes
        formate = new Formatter();
        formate.format("%tl:%tM", gfg_calender,
                       gfg_calender);

        // Printing the current hour and minute
        System.out.println(formate);
    }
}
```

**Output**

```
9:04

```

**方法 2:使用不带格式说明符的日历类**

[java.util.Calendar.get()](https://www.geeksforgeeks.org/calendar-get-method-in-java/) 方法是 java.util.Calendar 类的一个方法。Calendar 类提供了一些在包外实现具体日历系统的方法。日历字段的一些示例有:年、日、月、周、年、年、分、秒、小时、上午、下午、月、月、月、日。

下面是一个不使用格式说明符显示当前日期和时间的 java 示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Display
// current hour and minute

// Importing java Date class libraries
import java.util.Calendar;
import java.util.Formatter;

class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating a calendar using getInstance method
        Calendar now = Calendar.getInstance();

        // Get the current hour and minute as parameters
        System.out.println(now.get(Calendar.HOUR_OF_DAY)
                           + ":"
                           + now.get(Calendar.MINUTE));
        // Printing the current hour and minute using now
    }
}
```

**Output**

```
9:4

```