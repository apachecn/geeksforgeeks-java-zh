# Java.util.TimeZone 类(Set-2) |关于 TimeZone 类的示例

> 原文:[https://www . geesforgeks . org/Java-util-time zone-class-set-2-example-time zone-class/](https://www.geeksforgeeks.org/java-util-timezone-class-set-2-example-timezone-class/)

TimeZone 类(这个类的方法在本文中已经讨论过了 [Java.util.TimeZone 类| Set 1](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/) )可以在很多情况下使用，比如使用 TimeZone 类我们可以根据两个地方之间的小时和分钟来得到时差。
**问题:**我们如何从地球两个地方的小时和分钟来获得时差？
**解决方案:**要解决上述情况，必须按照以下步骤

1.  获取时区标识作为这两个地方的输入。
2.  使用此时区 Id 查找两个地方的时区。
3.  使用时区查找两个地方的日期和时间
4.  找出两个地方的日期和时间的差异
5.  不同的是你对上述问题的回答

你可以得到时区 id 列表，然后你可以去这个[链接](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)(这个[链接](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)的列名 TZ*的数据是时区 id。您可以使用这些标识作为输入。)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find time difference in term of hour and
// minute between two places.

import java.time.LocalDateTime;
import java.util.*;

public class TimeDifference {

    public static void main(String[] args)
    {

        // Take Ids of both places as Input
        Scanner sc = new Scanner(System.in);

        String TimeZoneId1 = sc.nextLine();
        String TimeZoneId2 = sc.nextLine();

        // Using Id of First place find LocalDateTime of that place
        TimeZone timezone1 = TimeZone.getTimeZone(TimeZoneId1);

        LocalDateTime dateTime1 = getDateTime(timezone1);

        // Using Id of Second place find LocalDateTime of that place
        TimeZone timezone2 = TimeZone.getTimeZone(TimeZoneId2);

        LocalDateTime dateTime2 = getDateTime(timezone2);

        // Print the Date and Time of Both TimeZones
        System.out.println("Date and Time of place having Id " + TimeZoneId1);
        System.out.println("Date - " + dateTime1.toLocalDate());
        System.out.println("Time - " + dateTime1.toLocalTime());
        System.out.println("Date and Time of place having Id " + TimeZoneId2);
        System.out.println("Date - " + dateTime2.toLocalDate());
        System.out.println("Time - " + dateTime2.toLocalTime());

        // Find the Difference in terms of minutes between both places
        long diffInMinutes =
            java.time.Duration.between(dateTime1, dateTime2).toMinutes();
        System.out.println("\nDifference in Hour is "
            + Math.abs(diffInMinutes / 60));
        System.out.println("Difference in Minute is "
            + Math.abs(diffInMinutes % 60));
    }

    static LocalDateTime getDateTime(TimeZone time)
    {

        // Using Time zone get calendar object
        Calendar cal = new GregorianCalendar(time);

        // using calendar object find the month, year, day, hour, minute
        int month = cal.get(Calendar.MONTH);
        int year = cal.get(Calendar.YEAR);
        int day = cal.get(Calendar.DAY_OF_MONTH);
        int hour = cal.get(Calendar.HOUR_OF_DAY);
        int minute = cal.get(Calendar.MINUTE);

        /*
         * construct LocalDateTime object
        using month, year, day, hour, minute
        */
        LocalDateTime dateTime = LocalDateTime.of(year, month + 1, day,
                                                  hour, minute);

        return dateTime;
    }
}
```

输入:

```java
Asia/Chita
Asia/Yangon
```

输出:

```java
Date and Time of place having Id Asia/Chita
Date - 2018-04-25
Time - 04:16
Date and Time of place having Id Asia/Yangon
Date - 2018-04-25
Time - 01:46

Difference in Hour is 2
Difference in Minute is 30
```

**解释:**我们使用作为输入提供的标识获取该地点的时区对象，然后使用方法获取该地点的当前日期和时间。方法 getDateTime 返回 LocalDateTime 对象我们可以使用 LocalDateTime 类的 toLocalDate()方法获取 Date，使用 LocalDateTime 类的 toLocalTime()方法获取 Time。
当我们有两个地方的当前日期和时间时，我们可以找到两个地方之间在小时和分钟方面的时差。