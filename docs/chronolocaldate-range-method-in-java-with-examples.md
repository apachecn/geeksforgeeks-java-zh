# Java 中的 ChronoLocalDate range()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-range-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-range-method-in-java-with-examples/)

**计时日期**界面的**范围()**方法用于获取作为参数的字段传递的有效值范围。此方法返回一个 ValueRange 对象，该对象包含字段的最小和最大有效值。当字段不受支持时，将引发异常。这个计时日期有助于提高返回范围的准确性。

**语法:**

```
public ValueRange range(TemporalField field)

```

**参数:**此方法接受一个单参数**字段**，该字段是要查询范围的字段。

**返回值:**此方法返回**值范围**，这是该字段的有效值范围，不为空。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** –If the range of the field cannot be obtained.
*   不受支持的 dtime type exception 唉哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟。

下面的程序说明了 range()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDate.range() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2018-12-06");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate: "
                           + localD);

        // get range of Days field
        // from ChronoLocalDate using range method
        ValueRange range
            = localD.range(ChronoField.DAY_OF_MONTH);

        // print range of DAY_OF_MONTH
        System.out.println("Range of DAY_OF_MONTH: "
                           + range);
    }
}
```

**输出:**

```
ChronoLocalDate: 2018-12-06
Range of DAY_OF_MONTH: 1 - 31

```

**程序二:**

```
// Java program to demonstrate
// ChronoLocalDate.range() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2018-12-06");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate: "
                           + localD);

        // get range of DAY_OF_YEAR field
        // from ChronoLocalDate using range method
        ValueRange range
            = localD.range(ChronoField.DAY_OF_YEAR);

        // print range of DAY_OF_YEAR
        System.out.println("Range of DAY_OF_YEAR: "
                           + range);
    }
}
```

**输出:**

```
ChronoLocalDate: 2018-12-06
Range of DAY_OF_YEAR: 1 - 365

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/temporal/temporalacessor . html # range-Java . time . temporal field-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#range-java.time.temporal.TemporalField-)