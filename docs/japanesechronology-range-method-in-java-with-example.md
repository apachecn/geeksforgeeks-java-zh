# Java 中的日本年代范围()方法，示例

> 原文:[https://www . geesforgeks . org/Japanese 年表-范围-java 中的方法-带示例/](https://www.geeksforgeeks.org/japanesechronology-range-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的 **range()** 方法用于从 chrono 类型的指定字段中获取的范围。

**语法:**

```java
public ValueRange range(ChronoField field)
```

**参数:**该方法以**型计时场**的场为参数。

**返回值:**该方法从指定的类型为 chrono 的字段中返回的范围。

以下是说明**范围()**方法的示例:

**例 1:**

```java
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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in LocalDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting the ValueRange for
            // given ChronoField
            // by using range() method
            ValueRange range
                = crono.range(ChronoField.ERA);

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

```java
Equivalent Range : -1 - 2

```

**例 2:**

```java
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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in LocalDate
            JapaneseChronology crono
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

```java
Equivalent Range : 1873 - 999999999

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese seriogram . html # range-Java . time . temporal . chronofield-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#range-java.time.temporal.ChronoField-)