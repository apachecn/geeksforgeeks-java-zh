# Java.util.TimeZone 类|设置 1

> 原文:[https://www . geesforgeks . org/Java-util-time zone-class-set-1/](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/)

TimeZone 类用于表示时区偏移量，还计算夏令时。
**什么是时区和时间偏移？**
“时区”是用来描述当前世界不同地区的时间。它是指世界上以经度划分的 24 个区域中的一个特定区域。在这些区域中的每一个区域内，都维护着标准版本的时间。

*   不同时区的计算基于它们与协调世界时或世界协调时的关系。
*   时间偏移是从世界时中减去或添加到世界时中以获得当前民用时间的时间量，无论是标准时间还是夏令时。
*   我们根据经度将整个地球从东到西分为 24 个不同的区域，因此每个区域宽 15 度。所以，地球上有 24 个不同的时区。每个时区宽 15 度，每个时区之间有一个小时的时差。
*   根据从格林威治子午线向东或向西的距离，您必须为经度上的每 15 度间隔添加或减去适当的时间。

**例如:**要查找特定位置的时区(以小时为单位)，可以取经度(以度为单位)除以 15。例如，105 E 等于 105/15，等于 7。这意味着时区比世界协调时或格林尼治时间早 7 小时，也可以标记为世界协调时+7。其中 7 是该位置的时间偏移。

**Java 中的时区类**

**班级申报**

```java
public abstract class TimeZone extends 
Object implements Serializable, Cloneable
```

**时区类的方法:**

*   **getavailable IDs()**–使用此方法可以获得所有可用的时区 id。

```java
Syntax : public static String[] getAvailableIDs()
```

*   **getavailable IDs(int rawOffset)**–使用此方法，您可以获得一个 ID 数组，其中该 ID 的时区具有以毫秒为单位的指定 GMT 偏移。

```java
Syntax : public static String[] getAvailableIDs(int rawOffset)
Parameters: rawOffset - the given time zone GMT offset in milliseconds.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for Demonstration of
// getAvailableIDs() and
// getAvailableIDs(int rawOffset ) methods
import java.util.TimeZone;

public class TimeZoneDemo {

    public static void main(String[] args)
    {

        // get all the  timezones ids defined by TimeZone class
        String[] availableTimezones = TimeZone.getAvailableIDs();

        // Print Total no of TimeZones
        System.out.println("Total No of Time Zone Available");

        System.out.println(availableTimezones.length);

        // get all the  timezones  whose offset is
        // 7200000 milliseconds means 2 hour
        String[] timezones = TimeZone.getAvailableIDs(7200000);

        // Print Total no of TimeZones
        System.out.println("No of Time Zone having time offset 2 hour");

        System.out.println(timezones.length);

        // print all timezones names
        System.out.println("Timezone names having time offset 2 hour");

        for (int i = 0; i < timezones.length; i++)
            System.out.println(timezones[i]);
    }
}
```

```java
Output:  
Total No of Time Zone Available
628
No of Time Zone having a time offset 2 hour
43
Timezone names having a time offset 2 hour
ART
Africa/Blantyre
Africa/Bujumbura
Africa/Cairo......
............
```

*   **getDefault()**–使用这个方法可以得到程序运行的时区。

```java
Syntax : public static TimeZone getDefault()
```

*   **getDisplayName()**–方法返回初始化时区的长标准时间名称。

```java
Syntax : public final String getDisplayName() 
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for Demonstration of
// getDefault() and getDisplayName() methods
import java.util.TimeZone;

public class TimeZoneDemo {

    public static void main(String[] args)
    {

        // Get your Local Time Zone Where this Program is Running.
        TimeZone timezone = TimeZone.getDefault();

        // Get the Name of Time Zone
        String LocalTimeZoneDisplayName = timezone.getDisplayName();

        // Print the Name of Time Zone
        System.out.println(LocalTimeZoneDisplayName);
    }
}
```

```java
Output:  
Coordinated Universal Time
```

*   **获取时区(字符串标识)**–该方法用于获取给定标识的时区。

```java
Syntax :public static TimeZone getTimeZone(String ID)
Parameters: ID - the ID for a TimeZone.
```

*   **getdstservice()**–方法返回要添加到本地标准时间的时间量，以获得本地挂钟时间。

```java
Syntax : public int getDSTSavings()
```

*   **getID()**–该方法用于获取该时区的 ID。

```java
Syntax : public String getID()
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for Demonstration of
// getTimeZone(String ID),
// getDSTSavings()  and getID() methods
import java.sql.Time;
import java.util.TimeZone;

public class TimeZoneDemo {

    public static void main(String[] args)
    {

        // creating Timezone object whose id is Europe/Berlin
        TimeZone timezone = TimeZone.getTimeZone("Europe/Berlin");

        // printing the Display Name of this timezone object
        System.out.println("Display Name");

        System.out.println(timezone.getDisplayName());

        // getting DST in milliseconds
        int timeInMilliseconds = timezone.getDSTSavings();

        System.out.println("\nDST of Europe/Berlin is");
        System.out.println(timezone.getDSTSavings());

        // get Id of your Default Time Zone
        TimeZone defaultTimezone = TimeZone.getDefault();

        System.out.println("\nThe id of default Time zone is");
        System.out.println(timezone.getID());
    }
}
```

```java
Output: 
Display Name
Central European Time

DST of Europe/Berlin is
3600000

The id of default Time zone is
Europe/Berlin
```

*   **getOffset(长日期)**–该方法用于在方法中返回该时区相对于经过日期的 UTC 的偏移量。

```java
Syntax : the method is used to return the offset of this time zone
 from UTC at the passed date in method.
Parameters: date - the date represented in milliseconds
 since January 1, 1970 00:00:00 GMT
```

*   **日亮时间(日期日期)**–如果给定日期在该时区的夏令时，则该方法返回真，否则返回假。

```java
Syntax :Syntax : public abstract boolean inDaylightTime(Date date)
Parameters:date - the given Date.
```

*   **observesDaylightTime()**–如果该时区当前处于夏令时，或者如果在未来任何时间从标准时间转换到夏令时，则该方法返回 true。

```java
Syntax :public boolean observesDaylightTime()
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for
// Demonstration of getOffset(long date),
// inDaylightTime(Date date)  and
// observesDaylightTime() methods
import java.sql.Time;
import java.util.*;

public class TimeZoneDemo {

    public static void main(String[] args)
    {

        // creating Timezone object whose id is Europe/Berlin
        TimeZone timezone = TimeZone.getTimeZone("Europe/Berlin");

        // printing offset value
        System.out.println("Offset value of Europe/Berlin:");

        System.out.println(timezone.getOffset(Calendar.ZONE_OFFSET));

        // create Date Object
        Date date = new Date(2017, 04, 16);

        // checking the date is in day light time of that Time Zone or not
        System.out.println("\nDate 16/04/2017 is in Day Light Time of");

        System.out.println("Timezone: timezone.getDisplayName()");
        System.out.println(timezone.inDaylightTime(date));

        // check this Time Zone observes Day Light Time or Not
        System.out.println("\nTimeZone name " + timezone.getDisplayName());

        System.out.println("Observes Day Light Time");
        System.out.println(timezone.observesDaylightTime());
    }
}
```

```java
Output:
Offset value of Europe/Berlin:
3600000

Date 16/04/2017 is in Day Light Time of
Timezone: timezone.getDisplayName()
true

TimeZone name Central European Time
Observes Day Light Time
true
```

*   **设置默认值(时区)**–用于设置 getDefault 方法返回的时区。

```java
Syntax : public static void setDefault(TimeZone zone)
Parameters: zone - the new default time zone
```

*   **设置标识(字符串标识)**–用于设置时区标识。

```java
Syntax :public void setID(String ID)
Parameters: ID - the new time zone ID.
```

*   **克隆()**–此方法用于创建此时区的副本

```java
Syntax : public Object clone()
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for Demonstration of
// setDefault(TimeZone zone),
// setID(String ID)  and clone() methods
import java.util.*;

public class TimeZoneDemo {

    public static void main(String[] args)
    {

        // My previous Default Time Zone is
        TimeZone DefaultTimeZone = TimeZone.getDefault();

        System.out.println("Current Default TimeZone:");
        System.out.println(DefaultTimeZone.getDisplayName());

        // Setting  Europe/Berlin as your Default Time Zone
        TimeZone timezone = TimeZone.getTimeZone("Europe/Berlin");

        timezone.setDefault(timezone);
        TimeZone NewDefaultTimeZone = TimeZone.getDefault();
        System.out.println("\nNew Default TimeZone:");
        System.out.println(NewDefaultTimeZone.getDisplayName());

        // change Id Europe/Berlin to Eur/Ber
        timezone.setID("Eur/Ber");

        System.out.println("\nNew Id of Europe/Berlin is");
        System.out.println(timezone.getID());

        // create copy of a time zone
        System.out.println("\nOriginal TimeZone ID:");

        System.out.println(timezone.getID());
        TimeZone clonedTimezone = (TimeZone)timezone.clone();
        System.out.println("Cloned TimeZone ID:");
        System.out.println(clonedTimezone.getID());
    }
}
```

```java
Output:
Current Default TimeZone:
India Standard Time

New Default TimeZone:
Central European Time

New Id of Europe/Berlin is
Eur/Ber

Original TimeZone ID:
Eur/Ber
Cloned TimeZone ID:
Eur/Ber
```

**示例:** **打印程序运行的任何给定输入时区的日期和时间。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// java.util.timezone class
import java.text.*;
import java.util.*;

public class TimeZoneDemo {

    public static void main(String[] args)
    {
        // Get your Local Time Zone Where this Program is Running.
        TimeZone timezone = TimeZone.getDefault();

        // Get the Name of Time Zone
        String LocalTimeZoneName = timezone.getDisplayName();

        // Initialize your Date Object and Date Format to represent your Date
        Date date = new Date();
        DateFormat dformat = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");

        // set your local time Zone to your Date Format time Zone
        dformat.setTimeZone(timezone);

        // Print Date and Time for your Time Zone
        System.out.println("Date and time of your Local Time Zone:");
        System.out.println(LocalTimeZoneName + ", " + dformat.format(date));
    }
}
```

```java
 Output: 
Date and time of your Local Time Zone:
Coordinated Universal Time, 2018-04-17 07:36:19
```

[参考–甲骨文文档](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getAvailableIDs(int))