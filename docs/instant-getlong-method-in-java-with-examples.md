# Java 中的 Instant getLong()方法，示例

> 原文:[https://www . geesforgeks . org/instant-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-getlong-method-in-java-with-examples/)

**即时类**的 **getLong(临时字段)**方法用于从该时刻获取作为参数传递的指定字段的长值。此方法立即查询字段的值，返回值将始终在字段值的有效范围内。当字段不受支持并且方法无法返回 int 值时，将引发异常。

**语法:**

```
public int getLong(TemporalField field)
```

**参数:**该方法接受一个参数**字段**，即要获取的字段。它不应为空。

**返回:**该方法返回该字段的**长**值。

**异常:**此方法抛出以下异常:

*   **[Date and Time Exception]** : If the value of this field cannot be obtained or it is beyond the valid range of this field.
*   **Unsupported Temporaltypeexception** : If this field is not supported or the range of values exceeds one int.
*   **Arithmetic exception** : If there is a numerical overflow.

下面的程序说明了 Instant.getLong()方法:

**程序 1:**

```
// Java program to demonstrate
// Instant.getLong(TemporalField field) method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T01:34:50.93Z");

        // get all enum of chronofield
        // and iterate through all enum values
        for (ChronoField field : ChronoField.values()) {

            try {
                // get long value of field
                long value = instant.getLong(field);
                System.out.println("field : " + field
                                   + " || value : " + value);
            }
            catch (Exception e) {

                System.out.println("field : " + field
                                   + " is not supported");
            }
        }
    }
}
```

**输出:**

```
field : NanoOfSecond || value : 930000000
field : NanoOfDay is not supported
field : MicroOfSecond || value : 930000
field : MicroOfDay is not supported
field : MilliOfSecond || value : 930
field : MilliOfDay is not supported
field : SecondOfMinute is not supported
field : SecondOfDay is not supported
field : MinuteOfHour is not supported
field : MinuteOfDay is not supported
field : HourOfAmPm is not supported
field : ClockHourOfAmPm is not supported
field : HourOfDay is not supported
field : ClockHourOfDay is not supported
field : AmPmOfDay is not supported
field : DayOfWeek is not supported
field : AlignedDayOfWeekInMonth is not supported
field : AlignedDayOfWeekInYear is not supported
field : DayOfMonth is not supported
field : DayOfYear is not supported
field : EpochDay is not supported
field : AlignedWeekOfMonth is not supported
field : AlignedWeekOfYear is not supported
field : MonthOfYear is not supported
field : ProlepticMonth is not supported
field : YearOfEra is not supported
field : Year is not supported
field : Era is not supported
field : InstantSeconds || value : 1546133690
field : OffsetSeconds is not supported

```

**程序二:**

```
// Java program to demonstrate
// Instant.getLong(TemporalField field) method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T01:34:50.93Z");

        // get Instant second value from this Instant
        // using getLong method
        long secondvalue
            = instant.getLong(
                ChronoField.INSTANT_SECONDS);

        // print result
        System.out.println("Instant Seconds: "
                           + secondvalue);
    }
}
```

**输出:**

```
Instant Seconds: 1546133690

```

**程序 3:** 获取不支持的临时异常

```
// Java program to demonstrate
// Instant.getLong(TemporalField field) method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T01:34:50.93Z");

        // try to find AMPM_OF_DAY
        // using ChronoField.AMPM_OF_DAY
        // in getLong method
        try {

            long secondvalue
                = instant.getLong(
                    ChronoField.AMPM_OF_DAY);
        }
        catch (Exception e) {

            // print exception
            System.out.println("Exception: " + e);
        }
    }
}
```

T5】输出:

```
Exception:
 java.time.temporal.UnsupportedTemporalTypeException:
 Unsupported field: AmPmOfDay

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # get(Java . time . temporal . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#getLong(java.time.temporal.TemporalField))