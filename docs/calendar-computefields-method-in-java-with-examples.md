# Java 中的 Calendar computeFields()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-computefields-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-computefields-method-in-java-with-examples/)

Calendar 类中的 **computeFields()** 方法用于将当前毫秒时间值 time 转换为字段[]中提到的日历字段值的转换操作。

**注意:**这允许将为日历对象设置的新时间与日历字段值同步。

**语法:**

```java
protected abstract void computeFields()
```

**参数:**该方法不取任何参数。

**返回值:**该方法不返回值。

下面的程序说明了 Calendar 类的 computeFields()方法的工作:
**例 1:**

```java
// Java Code to illustrate
// computeFields() Method

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
        // computeFields()
        calndr.set(GregorianCalendar.YEAR, 2016);
        calndr.computeFields();

        // Displaying the current date
        System.out.println("The recent"
                           + " date is: " + calndr.getTime());
    }
}
```

**Output:**

```java
The Current date is: Wed Feb 13 16:15:15 UTC 2019
The recent date is: Wed Feb 13 16:15:15 UTC 2019

```

**例 2:**

```java
// Java Code to illustrate
// computeFields() Method

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
        // computeFields()
        calndr.set(GregorianCalendar.YEAR, 2000);
        calndr.computeFields();

        // Displaying the current date
        System.out.println("The recent"
                           + " date is: " + calndr.getTime());
    }
}
```

**Output:**

```java
The Current date is: Wed Feb 13 16:15:18 UTC 2019
The recent date is: Wed Feb 13 16:15:18 UTC 2019

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # computeFields()](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#computeFields())