# Java 中的 ChronoLocalDate 查询()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-query-method-in-java-with-examples/)

**查询()**一个**计时日期**界面的方法，用于使用指定的查询作为参数查询该计时日期。作为参数传递的 TemporalQuery 对象定义了用于从该 ChronoLocalDate 获取结果的逻辑。

**语法:**

```
public <R> R 
    query(TemporalQuery<R> query)

```

**参数:**该方法只接受一个参数**查询**，即要调用的查询。

**返回值:**该方法返回查询结果，可能返回 null。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法查询。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了 query()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDate.query() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDate object
        ChronoLocalDate ld = LocalDate.parse("2018-12-31");

        // apply the query method of ChronoLocalDate class
        String value
            = ld.query(TemporalQueries.precision())
                  .toString();

        // print the result
        System.out.println("Precision value for ChronoLocalDate is "
                           + value);
    }
}
```

**Output:**

```
Precision value for ChronoLocalDate is Days

```

**程序 2:** 显示如果查询没有找到所需的对象，则返回空值。

```
// Java program to demonstrate
// ChronoLocalDate.query() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDate object
        ChronoLocalDate ld = LocalDate.parse("2018-12-31");

        // apply query method of ChronoLocalDate class
        // print the result
        System.out.println("Zone value for ChronoLocalDate is "
                           + ld.query(
                                 TemporalQueries.offset()));
    }
}
```

**Output:**

```
Zone value for ChronoLocalDate is null

```

**参考文献:**
[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldata . html # query-Java . time . temporal query-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#query-java.time.temporal.TemporalQuery-)