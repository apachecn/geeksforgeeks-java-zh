# Java 中的日历设置 FirstDayOfWeek()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-setfirst dayofweek-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-setfirstdayofweek-method-in-java-with-examples/)

Calendar 类中的**setfirst dayofweek(int day _ val)**方法用于使用本 Calendar 中的 *day_val* 设置一周的第一天。

**语法:**

```java
public void set(int *day_val*)
```

**参数:**该方法取整数类型的一个参数 **day_val** ，指一周的第一天。

**返回值:**该方法不返回值。

以下程序说明了日历类的 setFirstDayOfWeek()方法的工作:
**示例 1:**

```java
// Java code to illustrate
// setFirstDayOfWeek() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying first day of the week
        int first_day = calndr.getFirstDayOfWeek();
        System.out.println("The Current"
                           + " First day of the week: "
                           + first_day);

        // Changing the first day of week
        calndr.setFirstDayOfWeek(Calendar.THURSDAY);

        // Displaying the alternate day
        first_day = calndr.getFirstDayOfWeek();
        System.out.println("The new first"
                           + " day of the week: "
                           + first_day);
    }
}
```

**Output:**

```java
The Current First day of the week: 1
The new first day of the week: 5

```

**例 2:**

```java
// Java code to illustrate
// setFirstDayOfWeek() method

import java.util.*;
public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating calendar object
        Calendar calndr
            = new GregorianCalendar(2018, 6, 10);

        // Displaying first day of the week
        int first_day = calndr.getFirstDayOfWeek();
        System.out.println("The"
                           + " First day of the week: "
                           + first_day);

        // Changing the first day of week
        calndr.setFirstDayOfWeek(Calendar.MONDAY);

        // Displaying the alternate day
        first_day = calndr.getFirstDayOfWeek();
        System.out.println("The new first"
                           + " day of the week: "
                           + first_day);
    }
}
```

**Output:**

```java
The First day of the week: 1
The new first day of the week: 2

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # setfirst dayofweek-int-](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#setFirstDayOfWeek-int-)