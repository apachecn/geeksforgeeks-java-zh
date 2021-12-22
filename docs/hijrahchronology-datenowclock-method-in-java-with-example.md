# Java 中的 hijrah 年表 dateNow(时钟)方法，示例

> 原文:[https://www . geeksforgeeks . org/hijrah 年表-date now clock-in-Java-method-with-example/](https://www.geeksforgeeks.org/hijrahchronology-datenowclock-method-in-java-with-example/)

**Java . time . chrono . Hijrah 年表**类的 **dateNow()** 方法用于根据 Hijrah 日历系统从指定的时钟对象中获取当前的本地日期。

**语法:**

```java
public HijrahDate dateNow(Clock clock)
```

**参数**:该方法以时钟的对象为参数。

**返回值:**该方法根据 Hijrah 日历系统从指定的时钟对象返回本地日期。

以下是举例说明 **dateNow()** 方法的例子:

**例 1:**

```java
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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // creating and initializing clock object
            Clock clock = Clock.systemUTC();

            // getting HijrahDate for the
            // given clock object
            // by using dateNow() method
            HijrahDate date = crono.dateNow(clock);

            // display the result
            System.out.println("HijrahDate is: " + date);
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

```java
HijrahDate is: Hijrah-umalqura AH 1441-05-27

```

**例 2:**

```java
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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // creating and initializing clock object
            Clock clock = Clock.systemUTC();

            // setting clock
            clock = Clock.tick(clock,
                               Duration.ofDays(100));

            // getting HijrahDate for the
            // given clock object
            // by using dateNow() method
            HijrahDate date = crono.dateNow(clock);

            // display the result
            System.out.println("HijrahDate is: " + date);
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

```java
HijrahDate is: Hijrah-umalqura AH 1441-03-03

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/HijRahEr 年表. html # dateNow-Java . time . clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#dateNow-java.time.Clock-)