# Java 中的 ChronoLocalDateTime plus(long，TemporalUnit)，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-plus long-tempalalunit-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-pluslong-temporalunit-in-java-with-examples/)

**计时日期时间**界面的 **plus()** 方法用于返回该计时日期时间的副本，并添加指定数量的单位。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。

**语法:**

```
default ChronoLocalDateTime plus(long amountToSubtract, 
                                 TemporalUnit unit)
```

**参数:**该方法接受两个参数 **amountToSubtract** 可以为负数，也可以接受**单位**为要相加金额的单位，不为空。

**返回值:**该方法根据添加了指定金额的计时日期时间返回**计时日期时间**。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法添加
*   **算术异常**–如果出现数值溢出

下面的程序说明了 plus()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// ChronoLocalDateTime.plus() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ChronoLocalDateTime instance
        ChronoLocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation of this ChronoLocalDateTime
        System.out.println("Original ChronoLocalDateTime: "
                           + ldt.toString());

        // add 200 DAYS to ChronoLocalDateTime
        ChronoLocalDateTime value
            = ldt.plus(200, ChronoUnit.DAYS);

        // print result
        System.out.println("ChronoLocalDateTime after adding DAYS: "
                           + value);
    }
}
```

**Output:** 

```
Original ChronoLocalDateTime: 2019-12-31T19:15:30
ChronoLocalDateTime after adding DAYS: 2020-07-18T19:15:30
```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chronical datetime . html # plus-long-Java . time . templunit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#plus-long-java.time.temporal.TemporalUnit-)