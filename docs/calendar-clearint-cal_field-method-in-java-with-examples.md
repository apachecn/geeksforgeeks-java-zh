# Java 中日历清除(int cal_field)方法，示例

> 原文:[https://www . geesforgeks . org/calendar-clearint-cal _ field-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-clearint-cal_field-method-in-java-with-examples/)

[日历类](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/)中的**clear(int*cal _ field*)**方法用于设置给定的日历字段值，该日历的时间值未定义。
注意:日历类的实现可能使用默认字段值进行日期和时间计算。

**语法:**

```java
public final void clear(int *cal_field*)
```

**参数:**该方法取一个整数类型的参数 *cal_field* ，指的是待定义的字段值。

**返回值:**该方法不返回值。

下面的程序说明了 Calendar 类的 clear()方法的工作:
**例 1:**

```java
// Java Code to illustrate clear() Method

import java.util.Calendar;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the Current Date
        System.out.println("Current Date&Time: "
                           + calndr.getTime());

        // Clear method for undefining the month
        // of the calendar
        calndr.clear(Calendar.MONTH);

        // Displaying the final result
        System.out.println("After clear method: "
                           + calndr.getTime());
    }
}
```

**Output:**

```java
Current Date&Time: Wed Mar 27 09:03:26 UTC 2019
After clear method: Sun Jan 27 09:03:26 UTC 2019

```

**例 2:**

```java
// Java Code to illustrate clear() Method

import java.util.Calendar;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the Current Date
        System.out.println("Current Date&Time: "
                           + calndr.getTime());

        // Clear method for undefining the year
        // of the calendar
        calndr.clear(Calendar.YEAR);

        // Displaying the final result
        System.out.println("After clear method: "
                           + calndr.getTime());
    }
}
```

**Output:**

```java
Current Date&Time: Wed Mar 27 09:03:32 UTC 2019
After clear method: Fri Mar 27 09:03:32 UTC 1970

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # clear(int)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#clear(int))