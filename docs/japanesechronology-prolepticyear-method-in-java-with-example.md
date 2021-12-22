# Java 中的日本年表 prolepticYear()方法，示例

> 原文:[https://www . geeksforgeeks . org/Japanese seriogram-prolecopic year-in-Java-method-with-example/](https://www.geeksforgeeks.org/japanesechronology-prolepticyear-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的**prolepiecialiyear()**方法用于检索特定日本时代的日语系统中出现的 prolepiecialiyear。

**语法:**

```java
public int prolepticYear(Era era,
                         int yearOfEra)

```

**参数**:该方法以下列参数为参数。

*   **Age:** That is, the object of the Japanese era.
*   **yearofera:** is the year of a specific era in Japan.

**返回值:**此方法返回特定日本时代的日本系统中出现的**无产年**。

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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(
                    JapaneseEra.HEISEI,
                    1444);

            // display the result
            System.out.println("proleptic Year is: "
                               + proyear);
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
proleptic Year is: 3432

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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(
                    JapaneseEra.SHOWA, 1200);

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
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: Invalid yearOfEra value

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese seriogram . html # prolepiecialyear-Java . time . chrono . era-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#prolepticYear-java.time.chrono.Era-int-)