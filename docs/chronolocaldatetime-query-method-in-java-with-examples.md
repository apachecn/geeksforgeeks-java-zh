# Java 中的 ChronoLocalDateTime 查询()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-query-method-in-java-with-examples/)

**查询()**一个**chronolocaldetime**接口的方法是使用指定的查询作为参数来查询这个 chronolocaldetime。作为参数传递的 TemporalQuery 对象定义了用于从该 ChronoLocalDateTime 获取结果的逻辑。

**语法:**

```
default <R> R query(TemporalQuery<R> query)

```

**参数:**该方法只接受一个参数**查询**，即要调用的查询。

**返回值:**该方法返回查询结果，可能返回 null。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法查询。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了查询()的方法:
**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDateTime.query() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime lt
            = LocalDateTime.parse(
                "2018-10-25T23:12:31.123");

        // apply query() method
        // of ChronoLocalDateTime interface
        String value
            = lt.query(
                    TemporalQueries.precision())
                  .toString();

        // print the result
        System.out.println("Precision value"
                           + " for ChronoLocalDateTime is "
                           + value);
    }
}
```

**输出:**

```
Precision value for ChronoLocalDateTime is Nanos

```

**程序 2:** 显示如果查询没有找到所需的对象，则返回空值。

```
// Java program to demonstrate
// ChronoLocalDateTime.query() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime lt
            = LocalDateTime.parse(
                "2018-10-25T23:12:31.123");

        // apply query() method
        // of ChronoLocalDateTime interface
        // and print the result
        System.out.println("offset value "
                           + "for ChronoLocalDateTime is "
                           + lt.query(TemporalQueries.offset()));
    }
}
```

**输出:**

```
offset value for ChronoLocalDateTime is null

```

**参考文献:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html # query-Java . time . temporal query-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#query-java.time.temporal.TemporalQuery-)