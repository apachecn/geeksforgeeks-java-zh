# Java 中 HijrahDate from()方法，示例

> 原文:[https://www . geesforgeks . org/hijrahdate-from-in-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahdate-from-method-in-java-with-example/)

**Java . time . chrono . hijrahdate**类的 **from()** 方法用于根据特定时态对象的 hijrah 日历系统获取 hijrah 日期。

**语法:**

```java
public static HijrahDate from(
      TemporalAccessor temporal)

```

**参数**:该方法取**任意时态取值器**的对象，在此基础上形成回历日期。

**返回值:**该方法根据指定时态对象的回历系统返回**回历日期**。

以下是举例说明从()方法的**:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// from() method

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
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime
                      .parse(
                          "2018-10-25T23:12:31."
                          + "123+02:00[Europe/Paris]");

            // Creating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.from(zonedate);

            // Display the result
            System.out.println("HijrahDate: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**Output:**

```java
HijrahDate: Hijrah-umalqura AH 1440-02-16

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// from() method

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
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime.parse(
                    "2018-12-30T19:34:50.63");

            // Creating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.from(localdate);

            // Display the result
            System.out.println("HijrahDate: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**Output:**

```java
HijrahDate: Hijrah-umalqura AH 1440-04-23

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrahdate . html # from-Java . time . temporal accessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#from-java.time.temporal.TemporalAccessor-)