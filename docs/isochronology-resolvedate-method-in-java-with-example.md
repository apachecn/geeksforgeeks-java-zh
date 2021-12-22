# Java 中的等时分解()方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-resolved ate-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-resolvedate-method-in-java-with-example/)

**Java . time . chrono . isochronology**类的 **resolveDate()** 方法用于根据 Iso 日历通过在特定解析器样式的帮助下解析与地图中特定长值相关联的 chrono 字段来检索本地日期。

**语法:**

```java
public LocalDate resolveDate(
       Map fieldValues,
       ResolverStyle resolverStyle)
```

**参数:**该方法将以下参数作为参数:

*   **Field value:** This will contain the timing field.
*   **Parser Style:** This will parse the time field and provide the date.

**返回值:**该方法通过解析地图中与特定长值相关联的 Chrono 字段，借助特定的解析器样式，根据 Iso 日历返回本地日期。

以下示例说明了 **resolveDate()** 方法:

**例 1:**

```java
// Java program to demonstrate
// resolveDate() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // LocalDate Object
            LocalDate hidate
                = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // creating and initializing HashMap
            HashMap<TemporalField, Long> map
                = new HashMap<TemporalField, Long>();

            // putting element into HashMap
            map.put((TemporalField)
                        ChronoField.EPOCH_DAY,
                    30l);

            // getting the resolveDate with
            // SMART ResolverStyle
            // by using resolveDate() method
            hidate
                = crono.resolveDate(
                    map,
                    ResolverStyle.LENIENT);

            // display the result
            System.out.println("LocalDate is : "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出:**

```java
LocalDate is : 1970-01-31

```

**例 2:**

```java
// Java program to demonstrate
// resolveDate() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // LocalDate Object
            LocalDate hidate
                = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // creating and initializing HashMap
            HashMap<TemporalField, Long> map
                = new HashMap<TemporalField, Long>();

            // putting element into HashMap
            map.put((TemporalField)
                        ChronoField.HOUR_OF_AMPM,
                    2000l);

            // getting the resolveDate with
            // SMART ResolverStyle
            // by using resolveDate() method
            hidate
                = crono.resolveDate(
                    map,
                    ResolverStyle.LENIENT);

            // display the result
            System.out.println("LocalDate is : "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**输出:**

```java
LocalDate is : null

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # resolved ate-Java . util . map-Java . time . format . resolvers style-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#resolveDate-java.util.Map-java.time.format.ResolverStyle-)