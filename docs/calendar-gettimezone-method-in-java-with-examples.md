# Java 中的 Calendar getTimeZone()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-gettimezone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-gettimezone-method-in-java-with-examples/)

Calendar 类中的 **getTimeZone()** 方法用于返回本日历的当前时区。

**语法:**

```
public TimeZone getTimeZone()
```

**参数:**该方法不取任何参数。
**返回值:**该方法返回该日历对象的时区。

下面的程序说明了日历类 getTimeZone()方法的工作:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// getTimeZone() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Getting the time zone of calendar
        TimeZone time_zone = calndr.getTimeZone();

        // Displaying the current time zone
        System.out.println("The current Time zone is: "
                           + time_zone.getDisplayName());
    }
}
```

**Output:** 

```
The current Time zone is: Coordinated Universal Time
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// getTimeZone() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Getting the time zone of calendar
        TimeZone time_zone = calndr.getTimeZone();

        // Displaying the current time zone
        System.out.println("The current Time zone is: "
                           + time_zone.getDisplayName());

        // Changing the time zone
        calndr.setTimeZone(
            TimeZone.getTimeZone("GMT"));

        System.out.println("New TimeZone: "
                           + calndr.getTimeZone()
                                 .getDisplayName());
    }
}
```

**Output:** 

```
The current Time zone is: Coordinated Universal Time
New TimeZone: Greenwich Mean Time
```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # getTimeZone–](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#getTimeZone--)