# Java 中的 GregorianCalendar setTimeZone()方法

> 原文:[https://www . geesforgeks . org/gregoriancalendar-settimezone-method-in-Java/](https://www.geeksforgeeks.org/gregoriancalendar-settimezone-method-in-java/)

**java . util . gregoriancalendar . settimezone()**方法是 Java 中的内置方法，它根据传递的参数将当前时区修改为新的时区。

**语法:**

```java
public void setTimeZone(*TimeZone tz*)
```

**参数:**该方法采用指定新时区值的*时区*对象的一个参数 *tz* 。

**返回值:**此方法不返回值。

**例:**

```java
Input : IST
Output : India Standard Time

Input : UTC
Output : Coordinated Universal Time

```

下面的程序说明了 java 中的 Java . util . gregoriancalendar . settimezone()函数:

**程序 1:**

```java
// Java Program to  illustrate 
// GregorianCalendar.setTimeZone()
// function 

import java.io.*;
import java.util.*;

class GFG {
     public static void main(String[] args) {

      // Create a new calendar
      GregorianCalendar cal = (GregorianCalendar) 
                    GregorianCalendar.getInstance();

      // Display the current date and time
      System.out.println("" + cal.getTime());

      System.out.println("Current Time Zone : " + 
                    cal.getTimeZone().getDisplayName());

      // Convert to another time zone
      cal.setTimeZone(TimeZone.getTimeZone("CST"));
      System.out.println("New Time Zone : " + 
                    cal.getTimeZone().getDisplayName());
   }
}
```

**输出:**

```java
Wed Jul 25 11:11:14 UTC 2018
Current Time Zone : Coordinated Universal Time
New Time Zone : Central Standard Time

```

**程序二:**

```java
// Java Program to  illustrate 
// GregorianCalendar.setTimeZone()
// function 

import java.io.*;
import java.util.*;

class GFG {
     public static void main(String[] args) {

      // Create a new calendar
      GregorianCalendar cal = (GregorianCalendar) 
                    GregorianCalendar.getInstance();

      // Display the current date and time
      System.out.println("" + cal.getTime());

      System.out.println("Current Time Zone : " + 
                    cal.getTimeZone().getDisplayName());

      // Convert to another time zone
      cal.setTimeZone(TimeZone.getTimeZone("IST"));
      System.out.println("New Time Zone : " + 
                    cal.getTimeZone().getDisplayName());
   }
}
```

**输出:**

```java
Wed Jul 25 11:11:21 UTC 2018
Current Time Zone : Coordinated Universal Time
New Time Zone : India Standard Time

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/gregoriancalendar . html # setTimeZone()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#getTimeZone())