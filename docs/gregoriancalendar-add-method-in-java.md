# Java 中的 GregorianCalendar add()方法

> 原文:[https://www . geesforgeks . org/gregoriancalendar-add-method-in-Java/](https://www.geeksforgeeks.org/gregoriancalendar-add-method-in-java/)

**java . util . GregorianCalendar . add(int calendar field，int time)** 是 Java 中 Gregorian calendar 类的内置方法。该函数接受日历字段和要添加到该特定日历字段的时间量作为参数。根据日历规则，该方法根据其符号将指定的时间量添加或推断到指定的字段。

**语法:**

```java
public void add*(int calendarfield, int time)*
```

**参数:**该功能接受两个强制参数，如下所述:

*   *日历字段:*要修改的日历字段。
*   *时间:*需要添加的时间量。

**返回值:**这个方法没有返回值。

**异常:**如果**日历字段**具有值 *ZONE_OFFSET* 、 *DST_OFFSET* ，或者未知，或者如果任何日历字段具有超出范围的值，该方法将引发 *IllegalArgumentException* 。

**示例:**

```java
Current Date and Time : Mon Jul 23 12:46:05 UTC 2018

Input : calendarfied = GregorianCalendar.YEAR, time = 2
Output : Thu Jul 23 12:46:05 UTC 2020

Input : calendarfied = GregorianCalendar.MONTH, time = 16
Output : Sat Nov 23 12:46:45 UTC 2019

```

下面的程序说明了 java 中 Java . util . gregoriancalendar . add()方法的使用:
**程序 1:**

```java
// Java Program to demonstrate add() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a new calendar
        GregorianCalendar newcalendar = (GregorianCalendar)
                           GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println(" Current Date and Time : "
                           + newcalendar.getTime());
        // Adding two months to the current date
        newcalendar.add((GregorianCalendar.MONTH), 2);

        // Display the modified date and time
        System.out.println(" Modified Date and Time : "
                           + newcalendar.getTime());
    }
}
```

**Output:**

```java
Current Date and Time : Fri Aug 03 11:48:38 UTC 2018
 Modified Date and Time : Wed Oct 03 11:48:38 UTC 2018

```

**程序 2:**

```java
// Java Program to demonstrate add() method
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a new calendar
        GregorianCalendar newcalendar = (GregorianCalendar)
                           GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println(" Current Date and Time : "
                           + newcalendar.getTime());
        // Adding twenty years to the current date
        newcalendar.add((GregorianCalendar.YEAR), 20);
        // Display the modified date and time
        System.out.println(" Modified Date and Time : "
                           + newcalendar.getTime());
    }
}
```

**Output:**

```java
Current Date and Time : Fri Aug 03 11:48:40 UTC 2018
 Modified Date and Time : Tue Aug 03 11:48:40 UTC 2038

```

**程序 3:**

```java
// Java Program to illustrate
// GregorianCalendar.add()
// function 

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a new calendar
        GregorianCalendar newcalendar = (GregorianCalendar)
                           GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println(" Current Date and Time : "
                           + newcalendar.getTime());
        // Deducting 16 months to the current date
        newcalendar.add((GregorianCalendar.MONTH), -16);
        // Display the modified date and time
        System.out.println(" Modified Date and Time : "
                           + newcalendar.getTime());

        // Deducting twelve years to the current date
        newcalendar.add((GregorianCalendar.MONTH), -12);
        // Display the modified date and time
        System.out.println(" Modified Date and Time : "
                           + newcalendar.getTime());
    }
}
```

**Output:**

```java
Current Date and Time : Fri Aug 03 11:48:43 UTC 2018
 Modified Date and Time : Mon Apr 03 11:48:43 UTC 2017
 Modified Date and Time : Sun Apr 03 11:48:43 UTC 2016

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/gregoriancalendar . html # add()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#add(int, int))