# 将公历改为 Java 中的 simpledate format

> 原文:[https://www . geesforgeks . org/change-Gregorian-calendar-to-simpledateformat-in-Java/](https://www.geeksforgeeks.org/change-gregorian-calendar-to-simpledateformat-in-java/)

给定一个[格式的日期，将其更改为](https://www.geeksforgeeks.org/java-util-gregoriancalendar-class-java/)[简单日期格式](https://www.geeksforgeeks.org/java-simpledateformat-set-1/)。
**例:**

```java
Input: Sat Apr 28 13:36:37 UTC 2018
Output: 28-Apr-2018

Input: Wed Apr 03 20:49:45 IST 2019
Output: 03-Apr-2019
```

**进场:**

1.  获取[公历日期](https://www.geeksforgeeks.org/java-util-gregoriancalendar-class-java/)进行转换。
2.  创建一个简单日期格式的对象，用于存储转换后的日期
3.  现在使用 [格式()](https://www.geeksforgeeks.org/simpledateformat-format-method-in-java-with-examples/)方法将公历日期更改为[简单日期格式。](https://www.geeksforgeeks.org/java-simpledateformat-set-1/)
4.  此格式方法将只采用公历日期的日期部分作为参数。因此使用 getTime()方法，这个需要的日期被传递给 format()方法。

**以下是上述方法的实现:**
**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert
// GregorianCalendar to SimpleDateFormat

import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;

public class GregorianCalendarToCalendar {

    public static void convert(
        GregorianCalendar gregorianCalendarDate)
    {
        // Creating an object of SimpleDateFormat
        SimpleDateFormat formattedDate
            = new SimpleDateFormat("dd-MMM-yyyy");

        // Use format() method to change the format
        // Using getTime() method,
        // this required date is passed
        // to format() method
        String dateFormatted
            = formattedDate.format(
                gregorianCalendarDate.getTime());

        // Displaying grogorian date ia SimpleDateFormat
        System.out.print("SimpleDateFormat: "
                         + dateFormatted);
    }

    // Driver code
    public static void main(String[] args)
    {

        // Get the Gregorian Date to be converted.
        GregorianCalendar gcal = new GregorianCalendar();
        gcal.set(GregorianCalendar.YEAR, 2019);

        // In gregorian calendar month is started from 0
        // so for april month will be 03 not 04
        gcal.set(GregorianCalendar.MONTH, 03);

        gcal.set(GregorianCalendar.DATE, 03);

        // Displaying Current Date
        // using GregorianCalendar Class
        System.out.println("Gregorian date: "
                           + gcal.getTime());

        // Function to convert this to SimpleDateFormat
        convert(gcal);
    }
}
```

**Output:** 

```java
Gregorian date: Wed Apr 03 05:21:17 UTC 2019
SimpleDateFormat: 03-Apr-2019
```