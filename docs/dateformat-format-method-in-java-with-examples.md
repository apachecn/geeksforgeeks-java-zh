# Java 中的 DateFormat format()方法，带示例

> 原文:[https://www . geesforgeks . org/dateform-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-format-method-in-java-with-examples/)

Java 中 **DateFormat 类**的 **format()** 方法用于将给定日期格式化为日期/时间字符串。基本上，该方法用于将该日期和时间转换为特定格式，即 mm/dd/yyyy。

**语法:**

```java
public final String format(Date date)
```

**参数:**该方法取 date 对象类型的一个参数日期，指的是要产生字符串输出的日期。

**返回值:**该方法以 mm/dd/yyyy 的字符串格式返回日期或时间。

以下程序说明了日期格式的格式()方法:
**示例 1:**

```java
// Java code to illustrate format() method

import java.text.*;
import java.util.Calendar;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateInstance();

        // Initializing the calender Object
        Calendar cal = Calendar.getInstance();

        // Displaying the actual date
        System.out.println("The original Date: "
                           + cal.getTime());

        // Using format() method for conversion
        String curr_date
            = DFormat.format(cal.getTime());
        System.out.println("Formatted Date: "
                           + curr_date);
    }
}
```

**Output:**

```java
The original Date: Wed Mar 27 11:12:29 UTC 2019
Formatted Date: Mar 27, 2019

```

**例 2:**

```java
// Java code to illustrate format() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateTimeInstance(
                DateFormat.LONG, DateFormat.LONG,
                Locale.getDefault());

        // Initializing the calender Object
        Calendar cal = Calendar.getInstance();

        // Displaying the actual date
        System.out.println("The original Date: "
                           + cal.getTime());

        // Using format() method for conversion
        String curr_date
            = DFormat.format(cal.getTime());
        System.out.println("Formatted Date: "
                           + curr_date);
    }
}
```

**Output:**

```java
The original Date: Wed Mar 27 11:12:37 UTC 2019
Formatted Date: March 27, 2019 11:12:37 AM UTC

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # format(Java . util . date)](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#format(java.util.Date))