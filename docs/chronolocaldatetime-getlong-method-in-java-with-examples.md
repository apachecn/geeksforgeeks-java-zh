# Java 中的 ChronoLocalDateTime getLong()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-getlong-method-in-java-with-examples/)

Java 中**ChronalDateTiME**接口的 **getLong()** 方法用于将作为输入从该 ChronalDateTiME 传递的指定字段的值作为长值。此方法在此 ChronoLocalDateTime 中查询该字段的值，返回值将始终在该字段的有效值范围内。当字段不受支持并且方法无法返回 int 值时，将引发异常。

**语法:**

```
long getLong(TemporalField field)

```

**参数:**该方法接受单个参数**字段**，代表要获取的字段。这是一个强制参数，不应为空。

**返回值:**该方法为该字段返回一个 **int** 值。

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果无法获取字段的值或者该值超出了字段有效值的范围。
*   **unsupportedtemporaltypexception**:如果不支持该字段或者值的范围超过了一个整数。
*   **算术异常**:如果出现数值溢出。

下面的程序说明了 getLong()方法:
**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDateTime.getLong() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDateTime object
        ChronoLocalDateTime localDT
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // get all enum of chronofield
        // and iterate through all enum values
        for (ChronoField field : ChronoField.values()) {

            try {
                // get long value of field
                long value = localDT.getLong(field);
                System.out.println(field
                                   + " : "
                                   + value);
            }
            catch (Exception e) {
                System.out.println("e " + field);
            }
        }
    }
}
```

**Output:**

```
NanoOfSecond : 0
NanoOfDay : 69330000000000
MicroOfSecond : 0
MicroOfDay : 69330000000
MilliOfSecond : 0
MilliOfDay : 69330000
SecondOfMinute : 30
SecondOfDay : 69330
MinuteOfHour : 15
MinuteOfDay : 1155
HourOfAmPm : 7
ClockHourOfAmPm : 7
HourOfDay : 19
ClockHourOfDay : 19
AmPmOfDay : 1
DayOfWeek : 2
AlignedDayOfWeekInMonth : 3
AlignedDayOfWeekInYear : 1
DayOfMonth : 31
DayOfYear : 365
EpochDay : 18261
AlignedWeekOfMonth : 5
AlignedWeekOfYear : 53
MonthOfYear : 12
ProlepticMonth : 24239
YearOfEra : 2019
Year : 2019
Era : 1
e InstantSeconds
e OffsetSeconds

```

**程序 2:**

```
// Java program to demonstrate
// ChronoLocalDateTime.getLong() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDateTime object
        ChronoLocalDateTime localDT
            = LocalDateTime
                  .parse("2018-10-25T23:12:31.123");

        // try to find AMPM_OF_DAY
        // using ChronoField.AMPM_OF_DAY
        // in getLong method
        try {

            long value
                = localDT.getLong(
                    ChronoField.AMPM_OF_DAY);

            // print result
            System.out.println("AMPM_OF_DAY value: "
                               + value);
        }
        catch (Exception e) {

            // print exception
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
AMPM_OF_DAY value: 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/temporal/temporalacessor . html # getLong-Java . time . temporal field-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#getLong-java.time.temporal.TemporalField-)