# Java 中的等时距()方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-range-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-range-method-in-java-with-example/)

Java . time . chrono . isochronomics 类的 range()方法用于从类型为 ChronoField 的指定字段中获取的范围。

**语法:**

```
public ValueRange range(ChronoField field)
```

**参数:**该方法以 ChronoField 类型的字段为参数。

**返回值:**该方法从指定的类型为 chrono 的字段中返回的范围。

以下是说明**范围()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// range() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting the ValueRange for
            // given ChronoField
            // by using range() method
            ValueRange range
                = crono.range(
                    ChronoField.ERA);

            // display the result
            System.out.println(
                "Equivalent Range : "
                + range);
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
Equivalent Range : 0 - 1

```

**例 2:**

```
// Java program to demonstrate
// range() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting the ValueRange for
            // given ChronoField
            // by using range() method
            ValueRange range
                = crono.range(
                    ChronoField.YEAR);

            // display the result
            System.out.println(
                "Equivalent Range : "
                + range);
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
Equivalent Range : -999999999 - 999999999

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # range-Java . time . temporal . chronofield-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#range-java.time.temporal.ChronoField-)