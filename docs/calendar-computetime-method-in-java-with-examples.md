# Java 中的 Calendar computeTime()方法，示例

> 原文:[https://www . geeksforgeeks . org/calendar-computetime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-computetime-method-in-java-with-examples/)

Calendar 类中的 **computeTime()** 方法用于字段[]中当前日历字段值到毫秒时间值时间的转换操作。

**语法:**

```
protected abstract void computeTime()
```

**参数:**该方法不取任何参数。

**返回值:**该方法不返回值。

下面的程序说明了 Calendar 类的 computeTime()方法的工作:
**例 1:**

```
// Java Code to illustrate
// computeTime() Method

import java.util.*;

public class CalendarClassDemo
    extends GregorianCalendar {
    public static void main(String args[])
    {
        // Creating calendar object
        CalendarClassDemo calndr = new CalendarClassDemo();

        // Displaying the current date
        System.out.println("The Current "
                           + "date is: " + calndr.getTime());

        // Clearing the calendar
        calndr.clear();

        // Set a new year and call
        // computeTime()
        calndr.set(GregorianCalendar.YEAR, 2016);
        calndr.computeTime();

        // Displaying the current date
        System.out.println("The recent"
                           + " date is: " + calndr.getTime());
    }
}
```

**Output:**

```
The Current date is: Wed Feb 13 16:27:12 UTC 2019
The recent date is: Fri Jan 01 00:00:00 UTC 2016

```

**例 2:**

```
// Java Code to illustrate
// computeTime() Method

import java.util.*;

public class CalendarClassDemo
    extends GregorianCalendar {
    public static void main(String args[])
    {
        // Creating calendar object
        CalendarClassDemo calndr = new CalendarClassDemo();

        // Displaying the current date
        System.out.println("The Current "
                           + "date is: " + calndr.getTime());

        // Clearing the calendar
        calndr.clear();

        // Set a new year and call
        // computeTime()
        calndr.set(GregorianCalendar.YEAR, 2000);
        calndr.computeTime();

        // Displaying the current date
        System.out.println("The recent"
                           + " date is: " + calndr.getTime());
    }
}
```

**Output:**

```
The Current date is: Wed Feb 13 16:27:15 UTC 2019
The recent date is: Sat Jan 01 00:00:00 UTC 2000

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # computeTime()](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#computeTime())