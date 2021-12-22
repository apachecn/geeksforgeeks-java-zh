# Java 中的日历完成()方法，示例

> 原文:[https://www . geesforgeks . org/calendar-complete-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-complete-method-in-java-with-examples/)

Calendar 类中的 **complete()** 方法用于填充日历字段中任何未设置的字段。它遵循以下完成过程:

1.  首先，如果尚未计算时间值，则调用 computeTime()方法从日历字段值中计算时间值。
2.  其次，要计算所有日历字段值，使用 computeFields()方法。

**语法:**

```
protected void complete()
```

**参数:**该方法不取任何参数。

**返回值:**该方法不返回值。

下面的程序说明了 Calendar 类的 complete()方法的工作:
**例 1:**

```
// Java Code to illustrate
// complete() Method

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
        // complete()
        calndr.set(GregorianCalendar.YEAR, 2008);
        calndr.complete();

        // Displaying the current date
        System.out.println("The new"
                           + " date is: " + calndr.getTime());
    }
}
```

**Output:**

```
The Current date is: Wed Feb 13 15:39:33 UTC 2019
The new date is: Tue Jan 01 00:00:00 UTC 2008

```

**例 2:**

```
// Java Code to illustrate
// complete() Method

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
        // complete()
        calndr.set(GregorianCalendar.YEAR, 1996);
        calndr.complete();

        // Displaying the current date
        System.out.println("The new"
                           + " date is: " + calndr.getTime());
    }
}
```

**Output:**

```
The Current date is: Wed Feb 13 15:39:36 UTC 2019
The new date is: Mon Jan 01 00:00:00 UTC 1996

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # complete()](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#complete())