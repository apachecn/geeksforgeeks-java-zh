# GregorianCalendar getGregorianChange()方法

> 原文:[https://www . geeksforgeeks . org/gregoriancalendar-getgregorianchange-method/](https://www.geeksforgeeks.org/gregoriancalendar-getgregorianchange-method/)

**java . util . gregoriancalendar . getgregorianchange()**是 Java 中的一个内置方法，它返回公历更改日期，即从儒略历日期到公历日期的更改。默认为*1582 年 10 月 15 日(公历)*，但可以使用 setGregorianDate()函数更改为任何其他日期。所有以前的日期都出现在儒略历中。

**语法:**

```
public final Date getGregorianChange()
```

**参数:**函数不接受任何参数。

**返回值:**该函数返回*这个*公历日历实例的公历更改日期。

**示例:**

```
Input : Tue Jul 24 01:22:29 UTC 2018
Output : Fri Oct 15 00:00:00 UTC 1582

Input: Tue Jul 24 01:22:29 UTC 2018
        c.setGregorianChange(new Date());
Output : Tue Jul 24 01:22:29 UTC 2018

```

下面的程序说明了 Java . util . gregoriancalendar . getgregorianchange()函数:
**程序 1:**

```
// Java Program to illustrate getGregorianChange()
// function 
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a new calendar
        GregorianCalendar c = (GregorianCalendar)
                     GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println("Current Date and Time : "
                           + c.getTime());

        // Fetch Gregorian change and display it
        System.out.println("Gregorian Date change :"
                           + c.getGregorianChange());
    }
}
```

**Output:**

```
Current Date and Time : Fri Jul 27 12:38:41 UTC 2018
Gregorian Date change :Fri Oct 15 00:00:00 UTC 1582

```

**程序 2:**

```
// Java Program to illustrate getGregorianChange()
// function 

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a new calendar
        GregorianCalendar c = (GregorianCalendar)
                     GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println("Current Date and Time : "
                           + c.getTime());

        // Change to current date
        c.setGregorianChange(new Date());

        // Fetch and Display the result
        System.out.println("Gregorian Date change :"
                           + c.getGregorianChange());
    }
}
```

**Output:**

```
Current Date and Time : Fri Jul 27 12:38:44 UTC 2018
Gregorian Date change :Fri Jul 27 12:38:44 UTC 2018

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/gregoriancalendar . html # getGregorianChange()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#getGregorianChange())