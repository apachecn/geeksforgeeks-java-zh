# Java 中的 MinguoDate atTime()方法，示例

> 原文:[https://www . geeksforgeeks . org/minuodate-at time-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-attime-method-in-java-with-example/)

**Java . time . chrono . MinguoDate**类的 **atTime()** 方法用于将该 mingodate 时间与本地时间相加，以产生等效的日期和时间。

**语法:**

```
public final ChronoLocalDateTime
      atTime(LocalTime localTime)

```

**参数**:该方法以 **LocalTime** 类型的对象为参数。

**返回值:**该方法通过将该民国日期与经过的当地时间相加，返回时间地点日期时间。

以下是说明 **atTime()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// atTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // creating and initializing
            // TemporalAccessor object
            LocalTime localtime
                = LocalTime.now();

            // getting Chrono Local date time
            // by using atTime() method
            ChronoLocalDateTime<MinguoDate> date
                = hidate.atTime(localtime);

            // display the result
            System.out.println(
                "Chrono LocalDateTime is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
Chrono LocalDateTime is: Minguo ROC 109-04-20T14:28:17.085

```

**例 2:**

```
// Java program to demonstrate
// atTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // creating and initializing
            // TemporalAccessor object
            LocalTime localtime
                = LocalTime.of(8, 20);

            // getting Chrono Local date time
            // by using atTime() method
            ChronoLocalDateTime<MinguoDate> date
                = hidate.atTime(localtime);

            // display the result
            System.out.println(
                "Chrono LocalDateTime is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
Chrono LocalDateTime is: Minguo ROC 109-04-20T08:20

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # atTime-Java . time . local time-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#atTime-java.time.LocalTime-)