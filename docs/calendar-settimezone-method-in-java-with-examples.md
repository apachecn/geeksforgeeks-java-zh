# Java 中的日历设置时区()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-settimezone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-settimezone-method-in-java-with-examples/)

Calendar 类中的**setTimeZone(Time _ Zone)**方法以时区值为参数，修改或设置该 Calendar 所代表的时区。

**语法:**

```java
public void setTimeZone(TimeZone *time_zone*)
```

**参数:**该方法取日期类型的一个参数**时区**，指的是要设置的给定日期。

**返回值:**该方法不返回值。

以下程序说明了日历类 setTimeZone()方法的工作:
**示例 1:**

```java
// Java code to illustrate
// setTime() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String[] args)
    {

        // Creating calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the current time zone
        String tz_name = calndr.getTimeZone()
                             .getDisplayName();

        System.out.println("The Current Time"
                           + " Zone: " + tz_name);

        TimeZone time_zone
            = TimeZone.getTimeZone("GMT");

        // Modifying the time zone
        calndr.setTimeZone(time_zone);

        // Displaying the modified zone
        System.out.println("Modified Zone: "
                           + calndr.getTimeZone()
                                 .getDisplayName());
    }
}
```

**Output:**

```java
The Current Time Zone: Coordinated Universal Time
Modified Zone: Greenwich Mean Time

```

**例 2:**

```java
// Java code to illustrate
// setTimeZone() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String[] args)
    {

        // Creating calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the current time zone
        String tz_name = calndr.getTimeZone()
                             .getDisplayName();

        System.out.println("The Current Time"
                           + " Zone: " + tz_name);

        TimeZone time_zone
            = TimeZone.getTimeZone("Pacific/Tahiti");

        // Modifying the time zone
        calndr.setTimeZone(time_zone);

        // Displaying the modified zone
        System.out.println("Modified Zone: "
                           + calndr.getTimeZone()
                                 .getDisplayName());
    }
}
```

**Output:**

```java
The Current Time Zone: Coordinated Universal Time
Modified Zone: Tahiti Time

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # setTimeZone(Java . util . time zone)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#setTimeZone(java.util.TimeZone))