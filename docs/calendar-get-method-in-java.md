# Java 中的 Calendar.get()方法

> 原文:[https://www.geeksforgeeks.org/calendar-get-method-in-java/](https://www.geeksforgeeks.org/calendar-get-method-in-java/)

java.util.Calendar.get()方法是 **java.util.Calendar** 类的一个方法。Calendar 类提供了一些在包外实现具体日历系统的方法。日历字段的一些示例有:年、日、月、周、年、年、分、秒、小时、上午、下午、月、月、月、日。

**语法:**

```java
public int get(int field)

where, field represents the given calendar
field and the function returns the value of
given field.

```

**异常:**如果指定字段超出范围，则抛出*arrayindextofboundsexception*。

**应用程序:**
**示例 1:** 获取日期、月份、年份

```java
// Java code to implement calendar.get() function
import java.util.*;

class GFG {

// Driver code
public static void main(String[] args) {

    // creating a calendar
    Calendar c = Calendar.getInstance();

    // get the value of DATE field
    System.out.println("Day : " +
                        c.get(Calendar.DATE));

    // get the value of MONTH field
    System.out.println("Month : " +
                        c.get(Calendar.MONTH));

    // get the value of YEAR field
    System.out.println("Year : " + 
                        c.get(Calendar.YEAR));
}
}
```

输出:

```java
Day : 1
Month : 2
Year : 2018

```

**示例 2 :** 获取一周中的某一天、一年中的某一天、一月中的某一周、一年中的某一周。

```java
// Java Code of calendar.get() function
import java.util.*;

class GFG {

// Driver code
public static void main(String[] args) {

    // creating a calendar
    Calendar c = Calendar.getInstance();

    // get the value of DATE_OF_WEEK field
    System.out.println("Day of week : " + 
                        c.get(Calendar.DAY_OF_WEEK));

    // get the value of DAY_OF_YEAR field
    System.out.println("Day of year : " +
                        c.get(Calendar.DAY_OF_YEAR));

    // get the value of WEEK_OF_MONTH field
    System.out.println("Week in Month : " + 
                        c.get(Calendar.WEEK_OF_MONTH));

    // get the value of WEEK_OF_YEAR field
    System.out.println("Week in Year : " + 
                        c.get(Calendar.WEEK_OF_YEAR));

    // get the value of DAY_OF_WEEK_IN_MONTH field
    System.out.println("Day of Week in Month : " +
                        c.get(Calendar.DAY_OF_WEEK_IN_MONTH));
}
}
```

输出:

```java
Day of week : 5
Day of year : 60
Week in Month : 1
Week in Year : 9
Day of Week in Month : 1

```

**示例 3 :** 获取小时、分钟、秒和 AM_PM。

```java
// Implementation of calendar.get()
// function in Java
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a calendar
        Calendar c = Calendar.getInstance();

        // get the value of HOUR field
        System.out.println("Hour : " + c.get(Calendar.HOUR));

        // get the value of MINUTE field
        System.out.println("Minute : " + c.get(Calendar.MINUTE));

        // get the value of SECOND field
        System.out.println("Second : " + c.get(Calendar.SECOND));

        // get the value of AM_PM field
        System.out.println("AM or PM : " + c.get(Calendar.AM_PM));

        // get the value of HOUR_OF_DAY field
        System.out.println("Hour (24-hour clock) : " + c.get(Calendar.HOUR_OF_DAY));
    }
}
```

输出:

```java
Hour : 6
Minute : 51
Second : 53
AM or PM : 0
Hour (24-hour clock) : 6

```