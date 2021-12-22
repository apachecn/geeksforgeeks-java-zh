# Java 中的 MonthDay 查询()方法，示例

> 原文:[https://www . geesforgeks . org/month day-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-query-method-in-java-with-examples/)

**查询()**一个**月日**类的方法，用于使用指定的查询作为参数查询这个月日。作为参数传递的临时查询对象定义了用于从这个月日获得结果的逻辑。

**语法:**

```java
public <R> R query(TemporalQuery<R> query)

```

**参数:**该方法只接受一个参数**查询**，即要调用的查询。

**返回值:**该方法返回查询结果，可能返回 null。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** -If you can't query.
*   **Arithmetic exception** -If there is a numerical overflow.

下面的程序说明了 query()方法:

**程序 1:**

```java
// Java program to demonstrate
// MonthDay.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create MonthDay object
        MonthDay lt
            = MonthDay.parse("--12-09");

        // apply query method of MonthDay class
        String value
            = lt.query(
                    TemporalQueries.chronology())
                  .toString();

        // print the result
        System.out.println("chronology value"
                           + " for MonthDay is "
                           + value);
    }
}
```

**输出:**

```java
chronology value for MonthDay is ISO

```

**程序 2:** 显示如果查询没有找到所需的对象，则返回空值。

```java
// Java program to demonstrate
// MonthDay.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create MonthDay object
        MonthDay lt
            = MonthDay.parse("--12-07");

        // apply query method of MonthDay class
        // print the result
        System.out.println("offset value"
                           + " for MonthDay is "
                           + lt.query(
                                 TemporalQueries.offset()));
    }
}
```

**输出:**

```java
offset value for MonthDay is null

```

**参考文献:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # query(Java . time . temporal query)