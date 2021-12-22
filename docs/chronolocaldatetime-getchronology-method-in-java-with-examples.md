# Java 中的 ChronoLocalDateTime()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-get timer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-getchronology-method-in-java-with-examples/)

Java 中**ChronalDateTiME**接口的**getTehrography()**方法获取使用中的日历系统这个日期的年表。

**语法** :

```java
default Chronology getChronology()

```

**参数**:此方法不接受任何参数。

**返回值**:返回**年表**，不为空。

下面的程序举例说明了 Java 中的**gettimeroute()**方法:

**程序 1:**

```java
// Program to illustrate the getChronology() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        ChronoLocalDateTime date
            = LocalDateTime
                  .from(ZonedDateTime.now());

        System.out.println(date.getChronology());
    }
}
```

**输出:**

```java
ISO

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html # GetError–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#getChronology--)