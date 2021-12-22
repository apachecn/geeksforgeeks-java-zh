# Java 中的 GregorianCalendar getTimeZone()方法

> 原文:[https://www . geesforgeks . org/gregoriancalendar-gettimezone-method-in-Java/](https://www.geeksforgeeks.org/gregoriancalendar-gettimezone-method-in-java/)

**java . util . gregoriancalendar . gettimezone()**方法是 Java 中的内置方法，它获取时区并返回与*这个*日历关联的**时区对象**。

**语法:**

```java
public TimeZone getTimeZone()
```

**参数:**此方法不接受任何参数。
**返回值:**此方法返回一个**时区对象**，表示此日历的*时区。*

**示例:**

```java
Input : Mon Jul 23 19:45:33 UTC 2018
Output : Coordinated Universal Time

Input : Wed Oct 23 20:02:52 UTC 2019
        cal.setTimeZone(TimeZone.getTimeZone("CST"));
Output : Central Standard Time
```

下面的程序说明了 java 中的 Java . util . gregoriancalendar . gettimezone()函数:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to  illustrate
// GregorianCalendar.getTimeZone()
// function

import java.io.*;
import java.util.*;

class GFG {
     public static void main(String[] args) {

      // Create a new calendar
      GregorianCalendar cal = (GregorianCalendar)
                        GregorianCalendar.getInstance();

      //Display the current date and time
      System.out.println("Current Date and Time : "
                            + cal.getTime());

      /* Creating a Time Zone object and
         storing this TimeZone */
      TimeZone t = cal.getTimeZone();

      // Display the time zone
      System.out.println("Time Zone : " +
                        t.getDisplayName());
   }
}
```

**Output:** 

```java
Current Date and Time : Wed Jul 25 11:25:16 UTC 2018
Time Zone : Coordinated Universal Time
```

**程序 2:** 在本程序中，我们使用 [setTimeZone()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#setTimeZone()) 来更改当前时区，然后使用 getTimeZone()方法获取新时区。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to  illustrate
// GregorianCalendar.getTimeZone()
// function

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
      // Changing the current time zone                    
      cal.setTimeZone(TimeZone.getTimeZone("CST"));

      /* Creating a Time Zone object and
         storing the TimeZone */
      TimeZone t = cal.getTimeZone();

      // Display the time zone
      System.out.println("Time Zone : " +
                        t.getDisplayName());
   }
}
```

**Output:** 

```java
Current Date and Time : Wed Jul 25 11:25:22 UTC 2018
Time Zone : Central Standard Time
```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/util/gregoriancalendar . html # getTimeZone()T4】