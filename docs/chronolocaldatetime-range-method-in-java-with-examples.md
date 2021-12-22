# Java 中的 chronolocaldatimerange()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-range-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-range-method-in-java-with-examples/)

**计时本地日期时间**界面的**范围()**方法用于获取作为参数传递的字段的有效值范围。此方法返回一个 ValueRange 对象，该对象包含字段的最小和最大有效值。这个 ChronoLocalDateTime 有助于提高返回范围的准确性。当字段不受支持并且方法无法返回范围值时，将引发异常。

**语法:**

```java
default ValueRange range(TemporalField field)

```

**参数:**该方法接受一个单参数**字段**，该字段是获取取值范围的字段。

**返回值:**此方法返回**值范围**，这是该字段的有效值范围，不为空。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** –If the range of the field cannot be obtained.
*   不受支持的 dtime type exception 唉哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟。

下面的程序说明了 range()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.range() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDateTime object
        ChronoLocalDateTime localDT
            = LocalDateTime
                  .parse("2018-10-25T23:12:31.123");

        // print ChronoLocalDateTime
        System.out.println("ChronoLocalDateTime of Calcutta: "
                           + localDT);

        // get range of MILLI_OF_SECOND field
        // from ChronoLocalDateTime using range method
        ValueRange range
            = localDT.range(ChronoField.MILLI_OF_SECOND);

        // print range of MILLI_OF_SECOND
        System.out.println("Range of MILLI_OF_SECOND: "
                           + range);
    }
}
```

**输出:**

```java
ChronoLocalDateTime of Calcutta: 2018-10-25T23:12:31.123
Range of MILLI_OF_SECOND: 0 - 999

```

**程序二:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.range() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDateTime object
        ChronoLocalDateTime localDT
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // print ChronoLocalDateTime
        System.out.println("ChronoLocalDateTime of Calcutta: "
                           + localDT);

        // get range of NANO_OF_SECOND field
        // from localDateTime using range method
        ValueRange range
            = localDT.range(ChronoField.NANO_OF_SECOND);

        // print range of NANO_OF_SECOND
        System.out.println("Range of NANO_OF_SECOND: "
                           + range);
    }
}
```

**输出:**

```java
ChronoLocalDateTime of Calcutta: 2019-12-31T19:15:30
Range of NANO_OF_SECOND: 0 - 999999999

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/temporal/temporalacessor . html # range-Java . time . temporal field-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#range-java.time.temporal.TemporalField-)