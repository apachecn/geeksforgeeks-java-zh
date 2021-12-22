# Java 中的 Minguo 年表 isLeapYear()方法，示例

> 原文:[https://www . geeksforgeeks . org/Minguo 年表-islapyear-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguochronology-isleapyear-method-in-java-with-example/)

**Java . time . chrono . Minguo 年表**类的**IsLapyear()**方法用于区分闰年和非闰年。如果是闰年，它将返回真或假。

**语法:**

```
public boolean isLeapYear(long prolepticYear)

```

**参数:**该方法以**普理年**为参数，检查是否为闰年。

**返回值:**如果前一年是闰年，该方法返回**布尔值**为真，否则为假。

以下是说明**方法的示例:**

**例 1:**

```
// Java program to demonstrate
// isLeapYear() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // MinguoDate Object
        MinguoDate hidate
            = MinguoDate.now();

        // getting MinguoChronology
        // used in MinguoDate
        MinguoChronology crono
            = hidate.getChronology();

        // getting id of this Chronology
        // by using isLeapYear() method
        boolean flag = crono.isLeapYear(2016);

        // display the result
        if (flag)
            System.out.println(
                "this is leap year");
        else
            System.out.println(
                "this is non leap year");
    }
}
```

**输出:**

```
this is non leap year

```

**例 2:**

```
// Java program to demonstrate
// isLeapYear() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // MinguoDate Object
        MinguoDate hidate
            = MinguoDate.now();

        // getting MinguoChronology
        // used in MinguoDate
        MinguoChronology crono
            = hidate.getChronology();

        // getting id of this Chronology
        // by using isLeapYear() method
        boolean flag = crono.isLeapYear(2017);

        // display the result
        if (flag)
            System.out.println(
                "this is leap year");
        else
            System.out.println(
                "this is non leap year");
    }
}
```

**输出:**

```
this is leap year

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese seriogram . html # islapyear-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#isLeapYear-long-)