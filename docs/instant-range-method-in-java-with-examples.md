# Java 中的即时范围()方法，示例

> 原文:[https://www . geesforgeks . org/instant-range-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-range-method-in-java-with-examples/)

**即时类**的**范围()**方法有助于获取作为参数的字段传递的有效值范围。此方法返回 ValueRange 对象，该对象包含字段的最小和最大有效值。这一瞬间有助于提高返回范围的准确性。当字段不受支持且方法无法返回范围值时，将引发异常。

**语法:**

```
public ValueRange range(TemporalField field)
```

**参数:**该方法接受一个参数**字段**，该字段是获取取值范围的字段。

**返回:**此方法返回**值范围**，这是该字段的有效值范围，不为空。

**异常:**如果无法获得字段的范围，此方法将抛出以下异常:

*   **【 Abnormal date and time:**
*   **If this field is not supported, it is not supported.**

下面的程序说明了 range()方法:

**节目 1:**

```
// Java program to demonstrate
// Instant.range() method

import java.time.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-28T19:34:50.63Z");

        // print Instant
        System.out.println("Instant: "
                           + instant);

        // get range of MILLI_OF_SECOND field
        // from instant using range method
        ValueRange range
            = instant.range(ChronoField.MILLI_OF_SECOND);

        // print range of MILLI_OF_SECOND
        System.out.println("Range of MILLI_OF_SECOND: "
                           + range);
    }
}
```

**节目 2:**

```
// Java program to demonstrate
// Instant.range() method

import java.time.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-28T19:34:50.63Z");

        // print Instant
        System.out.println("Instant: "
                           + instant);

        // get range of NANO_OF_SECOND field
        // from instant using range method
        ValueRange range
            = instant.range(ChronoField.NANO_OF_SECOND);

        // print range of NANO_OF_SECOND
        System.out.println("Range of NANO_OF_SECOND: "
                           + range);
    }
}
```

**程序 3:** 获取不支持的临时异常

```
// Java program to demonstrate
// Instant.range() method

import java.time.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-28T19:34:50.63Z");

        // try to find range of era using ChronoField
        try {

            ValueRange secondvalue
                = instant.range(ChronoField.ERA);
        }
        catch (Exception e) {

            // print exception
            System.out.println("Exception: " + e);
        }
    }
}
```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # range(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#range(java.time.temporal.TemporalField))