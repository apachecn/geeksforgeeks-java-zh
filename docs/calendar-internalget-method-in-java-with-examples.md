# Java 中的 Calendar internalGet()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-internal get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-internalget-method-in-java-with-examples/)

Calendar 类中的**internal get(int*calndr _ field*)**方法用于返回给定日历字段的值作为参数。
*注:*操作不涉及任何归一化或验证。

**语法:**

```java
protected final int internalGet(int *calndr_field*)
```

**参数:**该方法取一个参数 *calndr_field* ，指的是要操作的日历字段。

**返回值:**该方法返回传递参数的值。

下面的程序说明了日历类的 internalGet()方法的工作:
**例 1:**

```java
// Java code to illustrate
// internalGet() method

import java.util.*;

public class CalendarDemo
    extends GregorianCalendar {
    public static void main(String args[])
    {

        // Creating a new calendar
        CalendarDemo calndr = new CalendarDemo();

        // Displaying the Current date
        System.out.println("The current date is: "
                           + calndr.getTime());

        // Getting the Month
        System.out.println("Month is: "
                           + calndr
                                 .internalGet(MONTH));

        // Getting the Year
        System.out.println("Year is: "
                           + calndr
                                 .internalGet(YEAR));
    }
}
```

**Output:**

```java
The current date is: Wed Feb 20 16:11:36 UTC 2019
Month is: 1
Year is: 2019

```

**例 2:**

```java
// Java code to illustrate
// internalGet() method

import java.util.*;

public class Calendar_Demo
    extends GregorianCalendar {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar_Demo calndr = new Calendar_Demo();

        // Displaying the current date
        System.out.println("Calendar: "
                           + calndr
                                 .getTime());

        // Displaying the year
        System.out.println("Year: "
                           + calndr
                                 .internalGet(YEAR));

        // Displaying the month
        System.out.println("Month: "
                           + calndr
                                 .internalGet(MONTH));

        // Displaying other credentials
        System.out.println("Day: "
                           + calndr
                                 .internalGet(DAY_OF_WEEK));
    }
}
```

**Output:**

```java
Calendar: Thu Feb 21 09:43:53 UTC 2019
Year: 2019
Month: 1
Day: 5

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # internal get-int-](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#internalGet-int-)