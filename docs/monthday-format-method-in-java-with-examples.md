# Java 中的 MonthDay 格式()方法，带示例

> 原文:[https://www . geesforgeks . org/month day-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-format-method-in-java-with-examples/)

Java 中**月日类**的 **format()** 方法使用指定的格式化程序格式化这个月日。

**语法:**

```java
public String format(DateTimeFormatter formatter)
```

**参数:**这个方法接受一个参数**格式化程序**，指定要使用的格式化程序，它不为空。

**返回:**函数返回格式化的日期字符串，不为空。

以下程序说明了**月日格式()**方法:

**程序 1:**

```java
// Program to illustrate the format() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2018);

        DateTimeFormatter formatter
            = DateTimeFormatter
                  .ofPattern("YYYY-MM-dd");

        System.out.println(formatter.format(dt1));
    }
}
```

**输出:**

```java
2018-12-06

```

**程序二:**

```java
// Program to illustrate the format() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--10-06");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2018);

        DateTimeFormatter formatter
            = DateTimeFormatter
                  .ofPattern("--MM-dd");

        System.out.println(formatter.format(dt1));
    }
}
```

**输出:**

```java
--10-06

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/monthday . html # format-Java . time . format . datetime formatter-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#format-java.time.format.DateTimeFormatter-)