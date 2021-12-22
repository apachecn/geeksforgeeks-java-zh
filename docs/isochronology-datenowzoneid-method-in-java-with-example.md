# Java 中的等时日期(ZoneId)方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-datenowzoneid-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-datenowzoneid-method-in-java-with-example/)

**Java . time . chrono . isochronology**类的 **dateNow()** 方法用于从指定时区的系统时钟中获取符合 Iso 日历系统的当前本地日期。

**语法:**

```java
public LocalDate dateNow(ZoneId zone)
```

**参数**:该方法以 id 区的**对象为参数。**

**返回值:**该方法从指定的时钟对象返回按照 Iso 日历系统的本地日期。

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
            // creating and initializing LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // creating and initializing ZoneId object
            ZoneId id = ZoneId.systemDefault();

            // getting LocalDate for the
            // given zoneid object
            // by using dateNow() method
            LocalDate date = crono.dateNow(id);

            // display the result
            System.out.println("LocalDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
LocalDate is: 2020-03-08

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
            // creating and initializing LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // creating and initializing ZoneId object
            ZoneId id = ZoneId.of("Europe/Paris");

            // getting LocalDate for the
            // given zoneid object
            // by using dateNow() method
            LocalDate date = crono.dateNow(id);

            // display the result
            System.out.println("LocalDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
LocalDate is: 2020-03-08

```

**参考:**T2