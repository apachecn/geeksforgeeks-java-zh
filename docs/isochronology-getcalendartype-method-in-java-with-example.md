# Java 中的等时 getCalendarType()方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-getcalendar type-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-getcalendartype-method-in-java-with-example/)

**Java . time . chrono . isochronology**类的 **getCalendarType()** 方法用于检索该 Iso 时间系统下的日历类型。
**语法:**

```java
public String getCalendarType?()
```

**参数:**此方法不接受任何参数作为参数。
**返回值:**该方法返回该 Iso 时间系统下的**类型日历**。
以下是举例说明 **getCalendarType()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getCalendarType() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // LocalDate Object
        LocalDate hidate
            = LocalDate.now();

        // getting IsoChronology
        // used in LocalDate
        IsoChronology crono
            = hidate.getChronology();

        // getting type of Calendar
        // by using getCalendarType() method
        String era = crono.getCalendarType();

        // display the result
        System.out.println("Type of Calendar : "
                           + era);
    }
}
```

**Output**

```java
Type of Calendar : iso8601

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getCalendarType() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // LocalDate Object
        LocalDate hidate
            = LocalDate.now(Clock.systemDefaultZone());

        // getting IsoChronology
        // used in LocalDate
        IsoChronology crono
            = hidate.getChronology();

        // getting type of Calendar
        // by using getCalendarType() method
        String era = crono.getCalendarType();

        // display the result
        System.out.println("Type of Calendar : "
                           + era);
    }
}
```

**Output**

```java
Type of Calendar : iso8601

```

**参考:**
[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # getCalendarType–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#getCalendarType--)