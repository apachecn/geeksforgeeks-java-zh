# Java 中 LocalTime 截断 To()方法，示例

> 原文:[https://www . geesforgeks . org/local time-截断到 java 中的方法-示例/](https://www.geeksforgeeks.org/localtime-truncatedto-method-in-java-with-examples/)

一个 **LocalTime** 类的**截断为()**方法用来获取这个 LocalTime 在指定单位下的值。此方法采用参数“单位”，即本地时间将被截断到的单位。它返回一个截断的不可变的 LocalTime，其值以指定的单位表示。

**语法:**

```java
public LocalTime truncatedTo(TemporalUnit unit)

```

**参数:**该方法接受单个参数**单位**，代表要截断到的单位，不应为空。

**返回值:**该方法返回一个基于该时间的**不可变的截断本地时间**，时间被截断，不为空。

**异常:**此方法抛出以下两个异常:

*   日期时间异常:(中文)。
*   **does not support** does not support

下面的程序说明了截断到()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.truncatedTo() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("21:45:36.13");

        // print instance
        System.out.println("LocalTime before"
                           + " truncate: "
                           + time);

        // truncate to ChronoUnit.MINUTES
        // means unit smaller than Minute
        // will be Zero
        LocalTime returnvalue
            = time.truncatedTo(ChronoUnit.MINUTES);

        // print result
        System.out.println("LocalTime after "
                           + " truncate: "
                           + returnvalue);
    }
}
```

**输出:**

```java
LocalTime before truncate: 21:45:36.130
LocalTime after  truncate: 21:45

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.truncatedTo() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:21:30.13");

        // print instance
        System.out.println("LocalTime before"
                           + " truncate: "
                           + time);

        // truncate to ChronoUnit.HOURS
        // means unit smaller than Hour
        // will be Zero
        LocalTime returnvalue
            = time.truncatedTo(ChronoUnit.HOURS);

        // print result
        System.out.println("LocalTime after "
                           + " truncate: "
                           + returnvalue);
    }
}
```

**输出:**

```java
LocalTime before truncate: 01:21:30.130
LocalTime after  truncate: 01:00

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html #截断到(Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#truncatedTo(java.time.temporal.TemporalUnit))