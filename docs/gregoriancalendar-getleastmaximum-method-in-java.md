# Java 中的 Gregorian calendar getlestmaximum()方法

> 原文:[https://www . geesforgeks . org/gregoriancalendar-getlestmaximum-method-in-Java/](https://www.geeksforgeeks.org/gregoriancalendar-getleastmaximum-method-in-java/)

**java . util . Gregoriancalendar . GetLestMaximum()**方法是 Java 中的一个内置函数，它返回日历字段的最低最大值，作为参数传递给这个 GregorianCalendar 实例的*函数。任何可能的时间值的最低最大值定义为 get 方法返回的最大值，同时考虑了 *getFirstDayOfWeek* 、*getminimaldaysinfirst week*、 *getGregorianChange* 和 *getTimeZone* 方法的当前值。
**语法:*** 

```java
public int getMaximum(*int calendarfield*)
```

**参数:**该函数接受一个整数类型的强制参数*日历字段*，该参数是指该函数将返回其最低最大值的日历字段。
**返回值:**该方法返回一个*整数*值，该值等于指定日历字段的最低最大值。
**举例:**

```java
Input : DAY_OF_MONTH
Output : 28

Input : WEEK_OF_MONTH
Output : 3
```

以下程序说明了*Java . util . gregoriancalendar . getmaximum()*功能:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate getLeastMaximum()

import java.io.*;
import java.util.*;

class GFG {
     public static void main(String[] args) {

      // Create a new calendar
      GregorianCalendar cal = (GregorianCalendar)
                  GregorianCalendar.getInstance();

      // Display the current date and time
      System.out.println("Current Date and Time : "
                                   + cal.getTime());

      // Get lowest maximum for WEEK_OF_MONTH
      int maxm = cal.getLeastMaximum(
                   GregorianCalendar.WEEK_OF_MONTH);
      System.out.println("Lowest Maximum for"+
                   " WEEK_OF_MONTH field :" + maxm);

      // Get lowest maximum for DAY_OF_MONTH
      maxm = cal.getLeastMaximum(
                    GregorianCalendar.DAY_OF_MONTH);
      System.out.println("Lowest Maximum for"+
                     " DAY_OF_MONTH field:" + maxm);
   }
}
```

**Output:** 

```java
Current Date and Time : Wed Aug 01 06:48:43 UTC 2018
Lowest Maximum for WEEK_OF_MONTH field :3
Lowest Maximum for DAY_OF_MONTH field:28
```