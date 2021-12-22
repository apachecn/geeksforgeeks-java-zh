# Java 中的 HijrahChronology eras()方法，示例

> 原文:[https://www . geesforgeks . org/hijrah 年表-eras-Java 中的方法-示例/](https://www.geeksforgeeks.org/hijrahchronology-eras-method-in-java-with-example/)

**Java . time . chrono . hijrah 年表**类的**纪元()**方法用于检索该特定 Hijrah 年表下的所有纪元。

**语法:**

```
public List eras()
```

**参数:**此方法不接受任何参数作为参数。

**返回值:**这个方法返回这个特定的 hijrah 年表下的所有时代。

以下是说明**纪元()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// eras() method

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

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting all HijrahEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // display the result
            System.out.println("HijrahEra is: "
                               + (list.iterator()).next());
        }
        catch (DateTimeException e) {
            System.out.println("HijrahEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
HijrahEra is: AH

```

**例 2:**

```
// Java program to demonstrate
// eras() method

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
            HijrahDate hidate
                = HijrahDate.now(
                    Clock.systemDefaultZone());

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting all HijrahEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // display the result
            System.out.println("HijrahEra is: "
                               + (list.iterator())
                                     .next());
        }
        catch (DateTimeException e) {
            System.out.println("HijrahEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
HijrahEra is: AH

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Hijrah 年代学. html # eras–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#eras--)