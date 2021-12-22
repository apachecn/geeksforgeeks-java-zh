# Java 中的 GregorianCalendar getMinimum()方法

> 原文:[https://www . geesforgeks . org/gregoriancalendar-get minimum-method-in-Java/](https://www.geeksforgeeks.org/gregoriancalendar-getminimum-method-in-java/)

**java . util . Gregoriancalendar . GetMinimal()**方法是 Java 中的内置函数，它返回作为参数传递给函数的特定日历字段的最小值。对于任何可能的时间值，它都是 get()方法返回的最小值，还要考虑 getFirstDayOfWeek()，getMinimalDaysInFirstWeek()，getGregorianChange()和 getTimeZone()方法的当前值。

**语法:**

```
public int getMinimum*(*int calendarfield*)*
```

**参数:**该函数接受一个整数类型的强制参数 *calendarfield* ，该参数的最小值*这个* GregorianCalender 实例将由该函数返回。

**返回值:**
该方法为*这个*公历实例返回指定日历字段的最小值。

**示例:**

```
Input : DAY_OF_MONTH
Output : 1

Input : WEEK_OF_MONTH
Output : 0

```

下面的程序说明了 Java . util . Gregoriancalendar . GetMinimum()函数的使用:

**程序 1:**

```
// Java Program to illustrate getMinimum() function 
// GregorianCalender

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

      // Display minimum for WEEK_OF_MONTH
      int minm = cal.getMinimum(GregorianCalendar.WEEK_OF_MONTH);
      System.out.println("Minimum for WEEK_OF_MONTH field :"
                                                   + minm);

      // Display minimum for DAY_OF_MONTH
      minm = cal.getMinimum(GregorianCalendar.DAY_OF_MONTH);
      System.out.println("Minimum for DAY_OF_MONTH field:"
                                                  + minm);
   }
}
```

**Output:**

```
Current Date and Time : Fri Jul 27 11:40:24 UTC 2018
Minimum for WEEK_OF_MONTH field :0
Minimum for DAY_OF_MONTH field:1

```

**程序 2:**

```
// Java Program to illustrate getMinimum() function 
// GregorianCalender

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

      // Display minimum for YEAR
      int minm = cal.getMinimum(GregorianCalendar.YEAR);
      System.out.println("Minimum for YEAR field :"
                                          + minm);

      // Display minimum for HOUR_OF_DAY
      minm = cal.getMinimum(GregorianCalendar.HOUR_OF_DAY);
      System.out.println("Minimum for HOUR_OF_DAY field :"
                                                  + minm);
   }
}
```

**Output:**

```
Current Date and Time : Fri Jul 27 11:40:28 UTC 2018
Minimum for YEAR field :1
Minimum for HOUR_OF_DAY field :0

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/gregoriancalendar . html # getMinimum()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#getMinimum(int))