# Java |当前日期和时间

> 原文:[https://www.geeksforgeeks.org/java-current-date-time/](https://www.geeksforgeeks.org/java-current-date-time/)

可以有多种方式打印当前日期和时间。
**使用** [**日期类**](https://www.geeksforgeeks.org/date-class-java-examples/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print current date and
// time using Date class.
import java.util.*;

public class Main {
    public static void main(String[] args)
    {
        Date d1 = new Date();
        System.out.println("Current date is " + d1);
    }
}
```

**Output:** 

```java
Current date is Sat Mar 24 18:22:46 UTC 2018
```

**使用** [**历类**](https://www.geeksforgeeks.org/calendar-get-method-in-java/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Code of calendar.get() function
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        Calendar c = Calendar.getInstance();
        System.out.println("Day of week : " +
                           c.get(Calendar.DAY_OF_WEEK));
        System.out.println("Day of year : " +
                            c.get(Calendar.DAY_OF_YEAR));
        System.out.println("Week in Month : " +
                            c.get(Calendar.WEEK_OF_MONTH));
        System.out.println("Week in Year : " +
                            c.get(Calendar.WEEK_OF_YEAR));
        System.out.println("Day of Week in Month : " +                    
                      c.get(Calendar.DAY_OF_WEEK_IN_MONTH));
        System.out.println("Hour : " + c.get(Calendar.HOUR));
        System.out.println("Minute : " + c.get(Calendar.MINUTE));
        System.out.println("Second : " + c.get(Calendar.SECOND));
        System.out.println("AM or PM : " + c.get(Calendar.AM_PM));
        System.out.println("Hour (24-hour clock) : " +
                           c.get(Calendar.HOUR_OF_DAY));
    }
}
```

**Output:** 

```java
Day of week : 7
Day of year : 83
Week in Month : 4
Week in Year : 12
Day of Week in Month : 4
Hour : 6
Minute : 22
Second : 48
AM or PM : 1
Hour (24-hour clock) : 18
```

我们可以使用日历和[格式化类](https://www.geeksforgeeks.org/formatted-output-in-java/)以特定的格式打印当前日期。