# Java 中的 GregorianCalendar 克隆()方法

> 原文:[https://www . geesforgeks . org/gregoriancalendar-clone-method-in-Java/](https://www.geeksforgeeks.org/gregoriancalendar-clone-method-in-java/)

使用 GregorianCalendar 类的**Java . util . Gregorian calendar . clone()**方法创建一个新对象，并将*这个* GregorianCalendar 实例的所有内容复制到新对象中。

**语法:**

```
public Object clone()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回*这个*对象的副本。

**示例:**

```
Input: Mon Jul 23 14:35:27 UTC 2018
Output: Mon Jul 23 14:35:27 UTC 2018

Input: Current Date and Time is Mon Jul 23 14:35:27 UTC 2018
       cal1.add((GregorianCalendar.MONTH), -7);
       cal1.clone();
Output: Sat Dec 23 14:36:42 UTC 2017

```

下面的程序说明了 Java . util . gregoriancalendar . clone()方法:
**程序 1:**

```
// Java Program to illustrate GregorianCalendar.clone()
// function 

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a new calendar
        GregorianCalendar cal = (GregorianCalendar)
                   GregorianCalendar.getInstance();

        // Display the date and time
        System.out.println("Date and Time in"
                +" cal object : "+ cal.getTime());

        GregorianCalendar newcalender = 
                          new GregorianCalendar();

        // Cloning the object
        newcalender = (GregorianCalendar)cal.clone();

        // Display date and time
        System.out.println("Date and Time in"+
        " newcalender object : "+ newcalender.getTime());
    }
}
```

**Output:**

```
Date and Time in cal object : Fri Aug 03 11:01:24 UTC 2018
Date and Time in newcalender object : Fri Aug 03 11:01:24 UTC 2018

```

**程序 2:**

```
// Java Program to illustrate 
// GregorianCalendar.clone()
// function 

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a new calendar
        GregorianCalendar cal1, cal2;

        cal1 = (GregorianCalendar)GregorianCalendar.
                                     getInstance();

        // Display the current date and time
        System.out.println("Current Date and Time : "
                                   + cal1.getTime());
        // Modifying the current date and time
        cal1.add((GregorianCalendar.MONTH), 2);

        // Cloning the object
        cal2 = (GregorianCalendar)cal1.clone();

        // Display date and time
        System.out.println("New Date and Time : "
                           + cal2.getTime());
    }
}
```

**Output:**

```
Current Date and Time : Fri Aug 03 11:01:27 UTC 2018
New Date and Time : Wed Oct 03 11:01:27 UTC 2018

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/gregoriancalendar . html # clone()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#clone())