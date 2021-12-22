# java.time.OffsetDateTime Class in Java

> 原文：[https://www.geeksforgeeks.org/java-time-offsetdatetime-class-in-java/](https://www.geeksforgeeks.org/java-time-offsetdatetime-class-in-java/)

[Java](https://www.geeksforgeeks.org/java/) is the most popular programming language and widely used programming language. Java is used in all kind of application like mobile application, desktop application, web application. In this Java [java.time.OffsetDate](https://www.geeksforgeeks.org/tag/java-offsetdatetime/), [Time class](https://www.geeksforgeeks.org/time-class-in-java-sql/) is imported which is an immutable representation of a date-time with an offset. This class stores all date and time fields, to a precision of nanoseconds, as well as the offset from UTC. For example, the value “22nd February 2021 at 01:55.19.123456789 +02:00” can be stored in an OffsetDateTime.

<figure class="table">

| Methods | Description |
| --- | --- |
| adjustInto(Temporal temporal) | This method adjusts the specified temporal object to have the same offset, date and time as this object. |
| atZoneSameInstant(ZoneId zone) | This method combines this date-time with a time-zone to create a ZonedDateTime ensuring that the result has the same instant. |
| atZoneSimilarLocal(ZoneId zone) | This method combines this date-time with a time-zone to create a ZonedDateTime trying to keep the same local date and time. |
|  compareTo(OffsetDateTime other) | This method compares this date-time to another date-time. |
| equals(Object obj) | It is used to checks if this date-time is equal to another date-time. |
| getMonth() | It is a method that is used to display the current month. |
| now() | It is a method used to obtain the current date and time from the system clock. |
| getYear() | It is a method that is used to display the current Year. |
| getDayOfWeek() | It is a method that is used to display the current day of the week.  |
| getHour() | It is a method that is used to display a specific hour. |
| getMinute() | It is a method that is used to display a specific minute. |
| getNano() | It is a method that displays a specific nanosecond. |
| getSecond() | It is a method that displays a specific second. |
|  equals(Object obj) | This method checks if this date-time is equal to another date-time. |
| format(DateTimeFormatter formatter) | This method formats this date-time using the specified formatter. |
| from(TemporalAccessor temporal) | This method obtains an instance of OffsetDateTime from a temporal object. |
| get(TemporalField field) | This method gets the value of the specified field from this date-time as an int. |
|  hashCode() | A hash code for this date-time. |
| isAfter(OffsetDateTime other) | This method checks if the instant of this date-time is after that of the specified date-time. |
| isBefore(OffsetDateTime other) | This method checks if the instant of this date-time is before that of the specified date-time. |
|  isEqual(OffsetDateTime other) | This method checks if the instant of this date-time is equal to that of the specified date-time. |
|  isSupported(TemporalField field) | This method checks if the specified field is supported. |
| isSupported(TemporalUnit unit) | This method checks if the specified unit is supported. |
|  withMinute(int minute) | This method returns a copy of this OffsetDateTime with the minute-of-hour altered. |
|  withYear(int year) | This method returns a copy of this OffsetDateTime with the year altered. |
| minusDays(long days) | This method returns a copy of this OffsetDateTime with the specified number of days subtracted. |
| minusHours(long hours) | This method returns a copy of this OffsetDateTime with the specified number of hours subtracted. |
| minusMinutes(long minutes) | This method returns a copy of this OffsetDateTime with the specified number of minutes subtracted. |
| minusMonths(long months) | This method returns a copy of this OffsetDateTime with the specified number of months subtracted. |
|  minusNanos(long nanos) | This method returns a copy of this OffsetDateTime with the specified number of nanoseconds subtracted. |
| minusSeconds(long seconds) | This method returns a copy of this OffsetDateTime with the specified number of seconds subtracted. |
| minusWeeks(long weeks) | This method returns a copy of this OffsetDateTime with the specified number of weeks subtracted. |
|  minusYears(long years) | This method returns a copy of this OffsetDateTime with the specified number of years subtracted. |
|  range(TemporalField field) | This method gets the range of valid values for the specified field. |
| timeLineOrder() | This method gets a comparator that compares two OffsetDateTime instances based solely on the instant. |

</figure>

Below is the implementation of the problem statement: **Year/ Month/ Day format**

## Java

```
// import java.time.OffsetDateTime class
import java.time.OffsetDateTime;

public class gfg1 {

    public static void main(String[] args)
    {
        // now() is a method used to obtain current
        // date and time from the system clock.
        OffsetDateTime offsetDateTime
            = OffsetDateTime.now();
        // Display the offsetDateTime which will
        // display all current date and time.
        System.out.println(offsetDateTime);
        // Display Year, Month and Day using methods
        System.out.println(
            "Year  : " + offsetDateTime.getYear()
            + "| Month : " + offsetDateTime.getMonth()
            + " |Day : " + offsetDateTime.getDayOfWeek());
    }
}
```

**Output**

```
2021-02-22T17:53:28.809568Z
Year  : 2021| Month : FEBRUARY |Day : MONDAY
```

Below is the implementation of the problem statement: **Hour/ Minute/ Second/ NanoSecond format**

## Java

```
// import java.time.OffsetDateTime class
import java.time.OffsetDateTime;

public class gfg1 {

    public static void main(String[] args)
    {

        // now() is a method used to obtain current
        // date and time from the system clock.
        OffsetDateTime offsetDateTime
            = OffsetDateTime.now();
        // Display the offsetDateTime which will
        // display all current date and time.
        System.out.println(offsetDateTime);
        // Display the Hour,Minute, Second and
        // Nanosecond using getHour(), getMinute(),
        // getSecond() and getNano()
        System.out.println(
            "Hour  : " + offsetDateTime.getHour()
            + " Minute : " + offsetDateTime.getMinute()
            + " Second : " + offsetDateTime.getSecond()
            + " NanoSecond : " + offsetDateTime.getNano());
    }
}
```

**Output**

```
2021-02-22T17:53:28.315232Z
Hour  : 17 Minute : 53 Second : 28 NanoSecond : 315232000
```

**Reference:**

[https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html)