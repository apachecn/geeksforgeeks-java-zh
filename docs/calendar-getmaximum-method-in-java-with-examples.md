# Java 中的 Calendar getMaximum()方法，示例

> 原文:[https://www . geesforgeks . org/calendar-get maximum-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-getmaximum-method-in-java-with-examples/)

calendar 类中的**getMaximum(int*calndr _ field*)**方法用于返回此 Calendar 实例的给定日历字段(int calndr_field)的最大值。

**语法:**

```java
public abstract int getMaximum(int *calndr_field*)
```

**参数:**该方法取一个参数 *calndr_field* ，指的是要操作的日历字段。

**返回值:**该方法返回传递的日历字段的最大值。

下面的程序说明了日历类的 getMaximum()方法的工作:
**例 1:**

```java
// Java code to illustrate
// getMaximum() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Getting the required months
        System.out.println("Required days: "
                           + calndr.get(Calendar.DAY_OF_WEEK));

        // Getting the lowest maximum month
        int max_day = calndr.getMaximum(Calendar.DAY_OF_WEEK);

        // Displaying the results
        System.out.println("The Maximum"
                           + " days: " + max_day);
    }
}
```

**例 2:**

```java
// Java code to illustrate
// getMaximum() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating a calendar
        Calendar calndr = new GregorianCalendar(2018, 6, 10);

        // Getting the required months
        System.out.println("Required Months: "
                           + calndr.get(Calendar.MONTH));

        // Getting the lowest maximum month
        int max_month = calndr.getMaximum(Calendar.MONTH);

        // Displaying the results
        System.out.println("The"
                           + " Maximum months: " + max_month);
    }
}
```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # getMaximum-int-](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#getMaximum-int-)