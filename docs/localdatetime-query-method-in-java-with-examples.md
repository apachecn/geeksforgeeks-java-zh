# Java 中的 LocalDateTime 查询()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-query-method-in-java-with-examples/)

**query()** 一个 **LocalDateTime** 类的方法，用于使用指定的查询作为参数来查询这个 LocalDateTime。作为参数传递的临时查询对象定义了用于从该本地日期时间获取结果的逻辑。

**语法:**

```
public <R> R query(TemporalQuery<R> query)

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
// LocalDateTime.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create LocalDateTime object
        LocalDateTime lt
            = LocalDateTime.parse(
                "2018-10-25T23:12:31.123");

        // apply query method of LocalDateTime class
        String value
            = lt.query(
                    TemporalQueries.precision())
                  .toString();

        // print the result
        System.out.println("Precision value"
                           + " for LocalDateTime is "
                           + value);
    }
}
```

**Output:**

```
Precision value for LocalDateTime is Nanos

```

**程序 2:** 显示如果查询没有找到所需的对象，则返回空值。

```
// Java program to demonstrate
// LocalDateTime.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create LocalDateTime object
        LocalDateTime lt
            = LocalDateTime.parse(
                "2018-10-25T23:12:31.123");

        // apply query method of LocalDateTime class
        // print the result
        System.out.println("offset value "
                           + "for LocalDateTime is "
                           + lt.query(TemporalQueries.offset()));
    }
}
```

**Output:**

```
offset value for LocalDateTime is null

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # query(Java . time . temporal query)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#query(java.time.temporal.TemporalQuery))