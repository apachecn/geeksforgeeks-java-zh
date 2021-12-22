# Java 中的 HijRahnological prolepiciyear()方法，示例

> 原文:[https://www . geeksforgeeks . org/hijrah 年表-prolecopic year-in-Java-method-with-example/](https://www.geeksforgeeks.org/hijrahchronology-prolepticyear-method-in-java-with-example/)

**Java . time . chrono . hijrah 年表**类的**prolepiecialyear()**方法用于检索出现在特定 hijrah 时代的 hijrah 系统中的 prolepiecialyear。

**语法:**

```java
public int prolepticYear(Era era,
                         int yearOfEra)

```

**参数**:该方法以下列参数为参数。

*   **Age:** That is, the object of the Hijra era.
*   **yearofera:** is the year of a specific hijri era.

**返回值:**该方法返回特定回历时代回历系统中出现的**预测年**。

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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(HijrahEra.AH, 1444);

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
proleptic Year is: 1444

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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(HijrahEra.AH, 1200);

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
proleptic Year is: 1200

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrah 年表. html # prolepicyear-Java . time . chrono . era-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#prolepticYear-java.time.chrono.Era-int-)