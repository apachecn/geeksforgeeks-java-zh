# Java 中的 chronolocaldeate getserratory()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-getserial-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-getchronology-method-in-java-with-examples/)

Java 中**ChronalDate**接口的**getTehrography()**方法获取这个日期的年表，就是 ISO 日历系统。

**语法** :

```java
public IsoChronology getChronology()

```

**参数**:此方法不接受任何参数。

**返回值**:返回 ISO 年表，不为空。

下面的程序举例说明了 Java 中的**获取时间表()**方法:

**程序 1** :

```java
// Program to illustrate the getChronology() method

import java.util.*;
import java.time.chrono.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        ChronoLocalDate dt
            = LocalDate.parse("2018-11-27");
        System.out.println(dt.getChronology());
    }
}
```

**输出:**

```java
ISO

```

**程序二** :

```java
// Program to illustrate the getChronology() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {

        ChronoLocalDate dt
            = LocalDate.parse("2018-02-21");
        System.out.println(dt.getChronology());
    }
}
```

**输出:**

```java
ISO

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldata . html # GetError–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#getChronology--)