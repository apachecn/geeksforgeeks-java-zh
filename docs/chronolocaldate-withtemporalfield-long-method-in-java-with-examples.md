# Java 中带(TemporalField，long)方法的 ChronoLocalDate，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-with temporal field-long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-withtemporalfield-long-method-in-java-with-examples/)

**使用**计时日期**界面的**方法，将计时日期的指定字段设置为新值，并返回新日期时间的副本。此方法可用于更改任何受支持的字段，如年、月或月中的某一天。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。
在某些情况下，更改指定的字段会导致结果日期时间无效，例如将月份从 1 月 31 日更改为 2 月会使当月的某一天无效。在这种情况下，字段负责解析日期。通常，它会选择以前的有效日期，在本例中是二月的最后一个有效日期。ChronoLocalDate 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```
public ChronoLocalDate with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法基于此返回一个设置了指定字段的 ChronoLocalDate。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **unsupportedtemporaltypexception**–如果不支持该字段。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了 with()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDate.with() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate local
            = LocalDate.parse(
                "2018-12-06");

        // print instance
        System.out.println("ChronoLocalDate before"
                           + " applying method: "
                           + local);

        // apply with method of ChronoLocalDate class
        ChronoLocalDate updatedlocal
            = local.with(
                ChronoField.DAY_OF_MONTH, 30);

        // print instance
        System.out.println("ChronoLocalDate after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
ChronoLocalDate before applying method: 2018-12-06
ChronoLocalDate after applying method: 2018-12-30

```

**参考文献:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldata . html # with-Java . time . temporal field-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#with-java.time.temporal.TemporalField-long-)