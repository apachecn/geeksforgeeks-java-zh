# Java 中的 LocalTime range()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-range-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-range-method-in-java-with-examples/)

**range()** 类的 **LocalTime** 方法用于获取字段的最小值和最大值范围，并将字段作为参数传递给该方法。此方法返回的值是该字段的值范围对象，并且该方法仅返回受本地时间对象支持的那些字段的值范围对象。因此，当该方法不支持该字段时，该方法将引发异常。

**语法:**

```
public ValueRange range(TemporalField field)

```

**参数:**该方法接受一个参数字段，即查询范围的字段。

**返回值:**此方法返回字段的有效值范围。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法获得字段的范围。
*   **unsupportedtemporaltypexception**–如果不支持该字段。

以下程序举例说明了 range()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalTime.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalTime objects
        LocalTime l1
            = LocalTime
                  .parse("09:21:12");

        // apply range() method of LocalTime class
        ValueRange result
            = l1.range(ChronoField.MILLI_OF_SECOND);

        // print results
        System.out.println("Range in MILLI_OF_SECOND: "
                           + result);
    }
}
```

**Output:**

```
Range in MILLI_OF_SECOND: 0 - 999

```

**程序 2:**

```
// Java program to demonstrate
// LocalTime.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalTime objects
        LocalTime l1
            = LocalTime
                  .parse("19:21:12");

        // apply range() method of LocalTime class
        ValueRange result
            = l1.range(ChronoField.MINUTE_OF_HOUR);

        // print results
        System.out.println("Range in MINUTE_OF_HOUR: "
                           + result);
    }
}
```

**Output:**

```
Range in MINUTE_OF_HOUR: 0 - 59

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # range(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#range(java.time.temporal.TemporalField))