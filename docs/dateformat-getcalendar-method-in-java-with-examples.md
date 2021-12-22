# Java 中的日期格式 getCalendar()方法，带示例

> 原文:[https://www . geesforgeks . org/dateform-get calendar-in-Java-method-with-examples/](https://www.geeksforgeeks.org/dateformat-getcalendar-method-in-java-with-examples/)

Java 中 **DateFormat 类**的 **getCalendar()** 方法用于获取与该日期/时间格式对象关联的日历。

**语法:**

```
public Calendar getCalendar()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回该日期格式对象的日历实例。

下面的程序说明了 getCalendar()方法在 Java 中的使用:
**示例 1:**

```
// Java code to illustrate
// getCalendar() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] argv)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateTimeInstance();

        // String formatting
        String str = DFormat.format(new Date());

        // Displaying the Calendar
        System.out.println(DFormat.getCalendar());
    }
}
```

**Output:**

```
java.util.GregorianCalendar[time=1553691245240, areFieldsSet=true, areAllFieldsSet=true,
lenient=true, zone=sun.util.calendar.ZoneInfo[id="Etc/UTC", offset=0, dstSavings=0,
useDaylight=false, transitions=0, lastRule=null], firstDayOfWeek=1, minimalDaysInFirstWeek=1,
ERA=1, YEAR=2019, MONTH=2, WEEK_OF_YEAR=13, WEEK_OF_MONTH=5, DAY_OF_MONTH=27, DAY_OF_YEAR=86,
DAY_OF_WEEK=4, DAY_OF_WEEK_IN_MONTH=4, AM_PM=1, HOUR=0, HOUR_OF_DAY=12, MINUTE=54, SECOND=5,
MILLISECOND=240, ZONE_OFFSET=0, DST_OFFSET=0]

```

**例 2:**

```
// Java code to illustrate
// getCalendar() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] argv)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = new SimpleDateFormat("MM/ dd/ yy");

        // String formatting
        String str = DFormat.format(new Date());

        // Displaying the Calendar
        System.out.println(DFormat.getCalendar());
    }
}
```

**Output:**

```
java.util.GregorianCalendar[time=1553691264669, areFieldsSet=true, areAllFieldsSet=true,
lenient=true, zone=sun.util.calendar.ZoneInfo[id="Etc/UTC", offset=0, dstSavings=0,
useDaylight=false, transitions=0, lastRule=null], firstDayOfWeek=1, minimalDaysInFirstWeek=1,
ERA=1, YEAR=2019, MONTH=2, WEEK_OF_YEAR=13, WEEK_OF_MONTH=5, DAY_OF_MONTH=27, DAY_OF_YEAR=86,
DAY_OF_WEEK=4, DAY_OF_WEEK_IN_MONTH=4, AM_PM=1, HOUR=0, HOUR_OF_DAY=12, MINUTE=54, SECOND=24,
MILLISECOND=669, ZONE_OFFSET=0, DST_OFFSET=0]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # getCalendar()](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#getCalendar())