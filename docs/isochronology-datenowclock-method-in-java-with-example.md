# Java 中的等时日期(时钟)方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-date now clock-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-datenowclock-method-in-java-with-example/)

**Java . time . chrono . isochronology**类的 **dateNow()** 方法用于根据 Iso 日历系统从指定的时钟对象中获取当前的本地日期。

**语法:**

```
public LocalDate dateNow(Clock clock)
```

**参数**:该方法以**时钟**的对象为参数。

**返回值:**该方法根据 Hijrah 日历系统从指定的时钟对象返回**本地日期**。

以下是举例说明 **dateNow()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// dateNow() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in localDate
            IsoChronology crono = hidate.getChronology();

            // creating and initializing clock object
            Clock clock = Clock.systemUTC();

            // getting LocalDate for the
            // given clock object
            // by using dateNow() method
            LocalDate date = crono.dateNow(clock);

            // display the result
            System.out.println("LocalDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
LocalDate is: 2020-03-08

```

**例 2:**

```
// Java program to demonstrate
// dateNow() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in localDate
            IsoChronology crono = hidate.getChronology();

            // creating and initializing clock object
            Clock clock = Clock.systemUTC();

            // setting clock
            clock = Clock.tick(clock,
                               Duration.ofDays(100));

            // getting LocalDate for the
            // given clock object
            // by using dateNow() method
            LocalDate date = crono.dateNow(clock);

            // display the result
            System.out.println("LocalDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
LocalDate is: 2020-02-08

```

**参考:**T2