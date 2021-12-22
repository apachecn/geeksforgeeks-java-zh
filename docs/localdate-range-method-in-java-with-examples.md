# Java 中的 LocalDate range()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-range-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-range-method-in-java-with-examples/)

**LocalDate** 类的 **range()** 方法用于获取作为参数传递的字段的有效值范围。此方法返回 ValueRange 对象，该对象包含字段的最小和最大有效值。当字段不受支持时，将引发异常。这个本地日期有助于提高返回范围的准确性。

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
// LocalDate.range() method

import java.time.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate localD
            = LocalDate.parse("2018-12-06");

        // print LocalDate
        System.out.println("LocalDate: "
                           + localD);

        // get range of Days field
        // from LocalDate using range method
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
LocalDate: 2018-12-06
Range of DAY_OF_MONTH: 1 - 31

```

**程序二:**

```
// Java program to demonstrate
// LocalDate.range() method

import java.time.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate localD
            = LocalDate.parse("2018-12-06");

        // print LocalDate
        System.out.println("LocalDate: "
                           + localD);

        // get range of DAY_OF_YEAR field
        // from LocalDate using range method
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
LocalDate: 2018-12-06
Range of DAY_OF_YEAR: 1 - 365

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # range(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#range(java.time.temporal.TemporalField))