# Java 中的等时法 prolepticYear()方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-prolepieciary year-in-Java-method-with-example/](https://www.geeksforgeeks.org/isochronology-prolepticyear-method-in-java-with-example/)

**Java . time . chrono . isochronology 类**的**prolepiecialyear()**方法用于检索特定回历时代的 Iso 系统中存在的 prolepiecialyear。

**语法:**

```java
public int prolepticYear(Era era,
                         int yearOfEra)
```

**参数:**该方法将以下参数作为参数。

*   **Era:** is the object of the iso era.
*   **yearofera:** This is the year of a specific iso era.

**返回值:**该方法返回特定 iso 时代的 iso 系统中存在的年份。

以下是说明**prolepiecialyear()**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// prolepticYear() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(IsoEra.CE, 2020);

            // display the result
            System.out.println("proleptic Year is: "
                               + proyear);
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
proleptic Year is: 2020

```

**例 2:**

```java
// Java program to demonstrate
// prolepticYear() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(IsoEra.BCE, 1980);

            // display the result
            System.out.println("proleptic Year is: "
                               + proyear);
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
proleptic Year is: -1979

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # prolecopieyear-Java . time . chrono . era-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#prolepticYear-java.time.chrono.Era-int-)