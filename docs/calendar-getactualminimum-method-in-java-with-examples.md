# Java 中的 Calendar getActualMinimum()方法，带示例

> 原文:[https://www . geeksforgeeks . org/calendar-getactuallminium-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-getactualminimum-method-in-java-with-examples/)

calendar 类的**getactuallminimum(int*field _ value*)**方法用于根据此 Calendar 的时间值返回指定日历字段可能具有的最小值。

**语法:**

```java
public int getActualMinimum(int *field_value*)
```

**参数:**该方法取整数类型的一个参数 **field_value** ，指需要返回最小值的日历。

**返回值:**该方法返回传递字段的最小值。

下面的程序说明了 Calendar 类的 getActualMinimum()方法的工作:
**例 1:**

```java
// Java Code to illustrate
// getActualMinimum() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Getting the Minimum value that
        // year field can have
        int yr
            = calndr.getActualMinimum(Calendar.YEAR);
        System.out.println("The Minimum year: "
                           + yr);

        // Getting the Minimum value that
        // month field can have
        int mon
            = calndr.getActualMinimum(Calendar.MONTH);
        System.out.println("The Minimum Month is: "
                           + mon);
    }
}
```

**Output:**

```java
The Minimum year: 1
The Minimum Month is: 0

```

**例 2:**

```java
// Java Code to illustrate
// getActualMinimum() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr
            = new GregorianCalendar(2018, 9, 2);

        // Getting the Minimum value that
        // year field can have
        int yr
            = calndr.getActualMinimum(Calendar.YEAR);
        System.out.println("The Minimum year: "
                           + yr);

        // Getting the Minimum value that
        // month field can have
        int mon
            = calndr.getActualMinimum(Calendar.MONTH);
        System.out.println("The Minimum Month is: "
                           + mon);
    }
}
```

**Output:**

```java
The Minimum year: 1
The Minimum Month is: 0

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # getactuallminimum(int)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#getActualMinimum(int))