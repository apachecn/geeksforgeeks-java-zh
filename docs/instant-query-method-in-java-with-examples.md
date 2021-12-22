# Java 中的即时查询()方法，示例

> 原文:[https://www . geesforgeks . org/instant-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-query-method-in-java-with-examples/)

**查询()**一个 **Instant** 类的方法，用于使用指定的查询作为参数来查询这个 Instant。作为参数传递的 TemporalQuery 对象定义了用于从该时刻获取结果的逻辑。

**语法:**

```
public <R> R query(TemporalQuery<R> query)

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
// Instant.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create Instant object
        Instant instant
            = Instant.parse("2018-12-31T10:15:30.00Z");

        // apply query method of Instant class
        String value
            = instant.query(TemporalQueries.precision())
                  .toString();

        // print the result
        System.out.println("Precision value for Instant is "
                           + value);
    }
}
```

**Output:**

```
Precision value for Instant is Nanos

```

**程序 2:** 显示如果查询没有找到所需的对象，则返回空值。

```
// Java program to demonstrate
// Instant.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create Instant object
        Instant instant
            = Instant.parse("2018-12-31T10:15:30.00Z");

        // apply query method of Instant class
        // print the result
        System.out.println("Zone value for Instant is "
                           + instant.query(TemporalQueries.offset()));
    }
}
```

**Output:**

```
Zone value for Instant is null

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # query(Java . time . temporal . temporal query)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#query(java.time.temporal.TemporalQuery))