# Java 中的 LocalDateTime range()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-range-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-range-method-in-java-with-examples/)

**range()** 类的 **LocalDateTime** 方法对于获取作为参数传递给该方法的字段的最小值和最大值作为 ValueRange 对象非常有用。此方法只为本地日期对象支持的字段返回值范围对象。所以当这个方法不支持这个字段时，这个方法就会抛出一个异常。

**语法:**

```java
public ValueRange range(TemporalField field)

```

**参数:**该方法接受一个参数字段，即查询范围的字段。

**返回值:**此方法返回字段的有效值范围。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法获得字段的范围。
*   **unsupportedtemporaltypexception**–如果不支持该字段。

以下程序举例说明了 range()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime objects
        LocalDateTime l1
            = LocalDateTime
                  .parse("2018-12-06T19:21:12");

        // apply range() method of LocalDateTime class
        ValueRange result
            = l1.range(ChronoField.MILLI_OF_SECOND);

        // print results
        System.out.println("Range in MILLI_OF_SECOND: "
                           + result);
    }
}
```

**Output:**

```java
Range in MILLI_OF_SECOND: 0 - 999

```

**程序 2:**

```java
// Java program to demonstrate
// LocalDateTime.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime objects
        LocalDateTime l1
            = LocalDateTime
                  .parse("2018-12-06T19:21:12");

        // apply range() method of LocalDateTime class
        ValueRange result
            = l1.range(ChronoField.DAY_OF_YEAR);

        // print results
        System.out.println("Range in DAY_OF_YEAR: "
                           + result);
    }
}
```

**Output:**

```java
Range in DAY_OF_YEAR: 1 - 365

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # range(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#range(java.time.temporal.TemporalField))