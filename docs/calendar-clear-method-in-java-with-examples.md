# Java 中的日历清除()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-clear-method-in-java-with-examples/)

Calendar 类中的 **clear()** 方法用于设置所有的日历字段值，该日历的时间值未定义。
**注意:**日历类的实现可能使用默认字段值进行日期和时间计算。

**语法:**

```
public final void clear()
```

**参数:**该方法不取任何参数。

**返回值:**该方法不返回值。

下面的程序说明了 Calendar 类的 clear()方法的工作:
**示例:**

```
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

        // Clear method for undefining the values
        // of the calendar
        calndr.clear();

        // Displaying the final result
        System.out.println("After clear method: "
                           + calndr.getTime());
    }
}
```

**Output:**

```
Current Date&Time: Tue Feb 12 13:01:42 UTC 2019
After clear method: Thu Jan 01 00:00:00 UTC 1970

```

**例 2:**

```
// Java Code to illustrate clone() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr1 = new GregorianCalendar(2018, 12, 2);

        // Displaying current calendar
        System.out.println("Original calendar: "
                           + calndr1.getTime());

        // Clear method for undefining the values
        // of the calendar
        calndr1.clear();

        // Displaying the final result
        System.out.println("After clear method: "
                           + calndr1.getTime());
    }
}
```

**Output:**

```
Original calendar: Wed Jan 02 00:00:00 UTC 2019
After clear method: Thu Jan 01 00:00:00 UTC 1970

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # clear()](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#clear())