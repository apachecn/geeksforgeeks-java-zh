# Java 中的 Calendar getActualMaximum()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-getactualmaximum-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-getactualmaximum-method-in-java-with-examples/)

calendar 类的**getActualMaximum(int*field _ value*)**方法用于根据此 Calendar 的时间值返回指定日历字段可能具有的最大值。

**语法:**

```
public int getActualMaximum(int *field_value*)
```

**参数:**该方法取整数类型的一个参数 **field_value** ，指需要返回最大值的日历。

**返回值:**该方法返回传递字段的最大值。

下面的程序说明了日历类 getActualMaximum()方法的工作:
**例 1:**

```
// Java Code to illustrate
// getActualMaximum() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar
        Calendar calndr
            = Calendar.getInstance();

        // Getting the maximum value that
        // year field can have
        int yr
            = calndr.getActualMaximum(Calendar.YEAR);
        System.out.println("The Maximum year: "
                           + yr);

        // Getting the maximum value that
        // month field can have
        int mon
            = calndr.getActualMaximum(Calendar.MONTH);
        System.out.println("The Maximum Month is: "
                           + mon);
    }
}
```

**Output:**

```
The Maximum year: 292278994
The Maximum Month is: 11

```

**例 2:**

```
// Java Code to illustrate
// getActualMaximum() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr
            = new GregorianCalendar(2018, 9, 2);

        // Getting the maximum value that
        // year field can have
        int yr
            = calndr.getActualMaximum(Calendar.YEAR);
        System.out.println("The Maximum year: "
                           + yr);

        // Getting the maximum value that
        // month field can have
        int mon
            = calndr.getActualMaximum(Calendar.MONTH);
        System.out.println("The Maximum Month is: "
                           + mon);
    }
}
```

**Output:**

```
The Maximum year: 292278993
The Maximum Month is: 11

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # getActualMaximum(int)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#getActualMaximum(int))