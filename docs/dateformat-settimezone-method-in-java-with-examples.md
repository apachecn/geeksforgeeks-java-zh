# Java 中的 DateFormat setTimeZone()方法，带示例

> 原文:[https://www . geesforgeks . org/dateform-settimezone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-settimezone-method-in-java-with-examples/)

**日期格式类**中的**设置时区()**方法用于设置该日期格式日历的时区。

**语法:**

```
public void setTimeZone(TimeZone *time_zone*)
```

**参数**:该方法取时区类型的一个参数*时区*，引用新时区。****

******返回值:**该方法不返回值。****

 ****下面的程序说明了 DateFormat 类的 setTimeZone()方法的工作:
**示例 1:**

```
// Java code to illustrate
// getTimeZone() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] argv)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateInstance();

        // Converting the dateformat to string
        String str = DFormat.format(new Date());

        // Original TimeZone
        System.out.println(
            "The original timezone is: "
            + DFormat.getTimeZone()
                  .getDisplayName());

        TimeZone time_zone
            = TimeZone.getTimeZone("GMT");

        // Modifying the time zone
        DFormat.setTimeZone(time_zone);

        // Getting the modified timezones
        System.out.println(
            "New TimeZone is: "
            + DFormat.getTimeZone()
                  .getDisplayName());
    }
}
```

**输出:**

```
The original timezone is: Coordinated Universal Time
New TimeZone is: Greenwich Mean Time

```**** 

**例 2:**

```
// Java code to illustrate
// getTimeZone() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] argv)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateInstance();

        // Converting the dateformat to string
        String str = DFormat.format(new Date());

        // Original TimeZone
        System.out.println(
            "The original timezone is: "
            + DFormat.getTimeZone()
                  .getDisplayName());

        TimeZone time_zone
            = TimeZone.getTimeZone("Pacific/Tahiti");

        // Modifying the time zone
        DFormat.setTimeZone(time_zone);

        // Getting the modified timezones
        System.out.println(
            "New TimeZone is: "
            + DFormat.getTimeZone()
                  .getDisplayName());
    }
}
```

**Output:**

```
The original timezone is: Coordinated Universal Time
New TimeZone is: Tahiti Time

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # setTimeZone(Java . util . time zone)](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#setTimeZone(java.util.TimeZone))