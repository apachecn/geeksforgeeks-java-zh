# Java 中的日本纪年纪元()方法，示例

> 原文:[https://www . geesforgeks . org/Japanese 年表-纪元-java 中的方法-带示例/](https://www.geeksforgeeks.org/japanesechronology-eras-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的**纪元()**方法用于检索该特定日本年表下的所有纪元。

**语法:**

```java
public List eras()
```

**参数:**此方法不接受任何参数作为参数。

**返回值:**这个方法返回这个特定的日本年表下的所有时代。

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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting all JapaneseEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // display the result
            System.out.println(
                "JapaneseEra is: "
                + (list.iterator()).next());
        }
        catch (DateTimeException e) {
            System.out.println(
                "JapaneseEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
JapaneseEra is: Meiji

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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting all JapaneseEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // getting list Iterator
            Iterator iter = list.iterator();

            // display the result
            System.out.println("List of IsoEra : ");
            for (int i = 0; i < 4; i++)
                System.out.println(iter.next());
        }
        catch (DateTimeException e) {
            System.out.println(
                "JapaneseEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
List of IsoEra : 
Meiji
Taisho
Showa
Heisei

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese seriogram . html # eras–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#eras--)