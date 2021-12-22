# Java 中的 ChronoZonedDateTime 查询()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-query-method-in-java-with-examples/)

**查询()**一个**时区数据时间**界面的方法，用于使用指定的查询作为参数查询该时区数据时间。作为参数传递的 TemporalQuery 对象定义了用于从该时区获取结果的逻辑。

**语法:**

```
default <R> R query(TemporalQuery<R> query)

```

**参数:**该方法只接受一个参数**查询**，即要调用的查询。

**返回值:**该方法返回查询结果，可能返回 null。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** -If you can't query.
*   **[Arithmetic exception](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)** -If there is a numerical overflow.

下面的程序说明了 query()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.query() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime zlt
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // apply the query method of ChronoZonedDateTime class
        String value
            = zlt.query(
                     TemporalQueries.precision())
                  .toString();

        // print the result
        System.out.println("Precision value"
                           + " for ChronoZonedDateTime is "
                           + value);
    }
}
```

**输出:**

```
Precision value for ChronoZonedDateTime is Nanos

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.query() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime zlt
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // apply query method of ChronoZonedDateTime class
        // print the result
        System.out.println("offset value for "
                           + "ChronoZonedDateTime is "
                           + zlt.query(
                                 TemporalQueries.offset()));
    }
}
```

**输出:**

```
offset value for ChronoZonedDateTime is +02:00

```

**参考文献:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html # query-Java . time . temporal query-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#query-java.time.temporal.TemporalQuery-)