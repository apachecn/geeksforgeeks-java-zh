# Java 中的等时年代()方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-eras-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-eras-method-in-java-with-example/)

**Java . time . chrono . isochronology**类的**纪元()**方法用于检索该特定 Iso 年表下的所有纪元。

**语法:**

```java
public List eras()
```

**参数:**此方法不接受任何参数作为参数。

**返回值:**该方法返回该特定 Iso 年表下的所有年代。

以下是说明**纪元()**方法的示例:

**例 1:**

```java
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
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting all IsoEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // display the result
            System.out.println("IsoEra is: "
                               + (list.iterator()).next());
        }
        catch (DateTimeException e) {
            System.out.println("IsoEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
IsoEra is: BCE

```

**例 2:**

```java
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
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting all IsoEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // getting list Iterator
            Iterator iter = list.iterator();

            // display the result
            System.out.println("List of IsoEra : "
                               + "\n"
                               + iter.next() + "\n"
                               + iter.next());
        }
        catch (DateTimeException e) {
            System.out.println("IsoEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
List of IsoEra : 
BCE
CE

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # eras–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#eras--)