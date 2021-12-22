# Java 中的 GregorianCalendar isLeapYear()方法

> 原文:[https://www . geeksforgeeks . org/gregoriancalendar-islapyear-method-in-Java/](https://www.geeksforgeeks.org/gregoriancalendar-isleapyear-method-in-java/)

**Java . util . Gregoriancalendar . IsLappyear()**方法确定作为参数传递给函数的给定年份是否是闰年，如果给定年份是闰年，则返回 true，否则返回 false。

**语法:**

```
public boolean isLeapYear*(int year)*
```

**参数:**该函数接受单个整数参数*年份*，代表该函数需要检查是否为闰年的年份。

**返回值:**该函数返回一个布尔值。如果作为参数传递的年份是闰年，则返回 true，否则返回 false。

**示例:**

```
Input : 2016
Output : true

Input : 2018
Output : false

```

下面的程序举例说明了 java 中的 Java . util . gregoriancalendar . islapyear()函数:

**程序 1:**

## Java

```
// Java Program to illustrate isLeapYear() function 
// of GregorianCalendar

import java.io.*;
import java.util.*;

class GFG {
     public static void main(String[] args) {

      // Create a new calendar
      GregorianCalendar c = (GregorianCalendar) 
                 GregorianCalendar.getInstance();

      // Display the current date and time
      System.out.println("Current Date and Time : "
                                 + c.getTime());

      int year = c.get(GregorianCalendar.YEAR);
      if(c.isLeapYear(year))
      {
           System.out.println(year + 
                          " is leap year");
      }
      else
      {
          System.out.println(year + 
                     " is Not a leap year");
      }
   }
}
```

**输出:**

```
Current Date and Time : Fri Jul 27 11:53:39 UTC 2018
2018 is Not a leap year

```

**程序二:**

## Java

```
// Java Program to illustrate isLeapYear() function 
// of GregorianCalendar

import java.io.*;
import java.util.*;

class GFG {
     public static void main(String[] args) {

      // Create a new calendar
      GregorianCalendar c = (GregorianCalendar) 
                GregorianCalendar.getInstance();

      // Display the current date and time
      System.out.println("" + c.getTime());

      // Modifying the current calendar
      c.add((GregorianCalendar.MONTH), -30);

      int year = c.get(GregorianCalendar.YEAR);
      if(c.isLeapYear(year))
      {
           System.out.println(year + " is leap year");
      }
      else
      {
          System.out.println(year + " is Not a leap year");
      }
   }
}
```

**输出:**

```
Fri Jul 27 11:53:41 UTC 2018
2016 is leap year

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/gregoriancalendar . html # islapyear()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#isLeapYear(int))