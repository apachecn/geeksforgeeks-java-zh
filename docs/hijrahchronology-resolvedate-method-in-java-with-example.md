# Java 中的 HijrahChronology resolveDate()方法，示例

> 原文:[https://www . geeksforgeeks . org/hijrah 年表-resolved ate-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-resolvedate-method-in-java-with-example/)

**Java . time . chrono .hijrah 年表**类的**resolved date()**方法用于根据伊斯兰回历检索本地日期，方法是借助特定的 resolver 样式解析地图中与特定长值相关联的时间字段。

**语法:**

```
public HijrahDate resolveDate(Map fieldValues,
                              ResolverStyle resolverStyle)

```

**参数**:该方法将以下参数作为参数:

*   **Field value:** This will contain the timing field.
*   **Parser Style:** This will parse the time field and provide the date.

**返回值:**该方法通过在特定解析器样式的帮助下解析地图中与特定长值相关联的 Chrono 字段，根据伊斯兰回历返回**本地日期**。

以下示例说明了 **resolveDate()** 方法:

**例 1:**

```
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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // creating and initializing HashMap
            HashMap<TemporalField, Long> map
                = new HashMap<TemporalField, Long>();

            // putting element into HashMap
            map.put((TemporalField)ChronoField
                        .EPOCH_DAY,
                    1000l);
            map.put((TemporalField)ChronoField
                        .HOUR_OF_AMPM,
                    2000l);
            map.put((TemporalField)ChronoField
                        .HOUR_OF_DAY,
                    3000l);

            // getting the resolveDate with
            // SMART ResolverStyle
            // by using resolveDate() method
            hidate
                = crono.resolveDate(
                    map,
                    ResolverStyle.SMART);

            // display the result
            System.out.println("HijrahDate is : "
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

```
HijrahDate is : Hijrah-umalqura AH 1392-08-19

```

**例 2:**

```
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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
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
            System.out.println("HijrahDate is : "
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

```
HijrahDate is : null

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/HijRahEr 年表. html # resolved ate-Java . util . map-Java . time . format . resolver style-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#resolveDate-java.util.Map-java.time.format.ResolverStyle-)