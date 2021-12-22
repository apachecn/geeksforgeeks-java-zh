# Java 中的 Minguo 年表 prolepticYear()方法，示例

> 原文:[https://www . geeksforgeeks . org/Minguo 年表-prolecopic year-in-Java-method-with-example/](https://www.geeksforgeeks.org/minguochronology-prolepticyear-method-in-java-with-example/)

**Java . time . chrono . Minguo 年表**类的**prolepiecialiyear()**方法用于检索出现在特定民国时代的民国系统中的 prolepiecialiyear。

**语法:**

```
public int prolepticYear(Era era,
                         int yearOfEra)

```

**参数**:该方法以下列参数为参数。

*   **Age:** That is, the object of the Republic of China.
*   **yearofera:** is the year of the Republic of China.

**返回值:**此方法返回特定民国时代民国系统中出现的**无产年**。

以下是说明**prolepiecialyear()**方法的示例:

**例 1:**

```
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
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(
                    MinguoEra.ROC,
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

```
proleptic Year is: 1444

```

**例 2:**

```
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
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(
                    MinguoEra.BEFORE_ROC,
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

```
proleptic Year is: -1443

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguoserterog . html # prolepiecialyear-Java . time . chrono . era-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#prolepticYear-java.time.chrono.Era-int-)