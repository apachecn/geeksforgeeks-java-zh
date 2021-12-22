# Java 中的 Calendar get()方法，示例

> 原文:[https://www . geesforgeks . org/calendar-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-get-method-in-java-with-examples/)

Calendar 类的**get(int*field _ value*)**方法用于返回参数中给定日历字段的值。

**语法:**

```
public int get(int field)
```

**参数:**该方法取整数类型的一个参数 **field_value** ，指需要返回其值的日历。

**返回值:**该方法返回传递字段的值。

下面的程序说明了日历类 get()方法的工作:
**例 1:**

```
// Java Code to illustrate
// get() Method

import java.util.*;

public class CalendarClassDemo
    extends GregorianCalendar {
    public static void main(String args[])
    {
        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Getting the value of all
        // the calendar date fields
        System.out.println("The given calendar's"
                           + " year is: " + calndr.get(Calendar.YEAR));
        System.out.println("The given calendar's"
                           + " month is: " + calndr.get(Calendar.MONTH));
        System.out.println("The given calendar's"
                           + " day is: " + calndr.get(Calendar.DATE));
    }
}
```

**Output:**

```
The given calendar's year is: 2019
The given calendar's month is: 1
The given calendar's day is: 13

```

**例 2:**

```
// Java Code to illustrate
// get() Method

import java.util.*;

public class CalendarClassDemo
    extends GregorianCalendar {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr = new GregorianCalendar(2018, 9, 2);

        // Getting the value of all
        // the calendar date fields
        System.out.println("The given calendar's"
                           + " year is: " + calndr.get(Calendar.YEAR));
        System.out.println("The given calendar's"
                           + " month is: " + calndr.get(Calendar.MONTH));
        System.out.println("The given calendar's"
                           + " day is: " + calndr.get(Calendar.DATE));
    }
}
```

**Output:**

```
The given calendar's year is: 2019
The given calendar's month is: 9
The given calendar's day is: 2

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # get(int)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#get(int))