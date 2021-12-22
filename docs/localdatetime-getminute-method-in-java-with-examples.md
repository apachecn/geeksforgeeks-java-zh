# Java 中的 LocalDateTime getMinute()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-get minute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-getminute-method-in-java-with-examples/)

**本地日期时间类**的 **getMinute()** 方法用于返回小时分钟字段。此方法返回一个 0 到 59 之间的整数值，即一小时的分钟数。

**语法:**

```java
public int getMinute()

```

**参数:**此方法不接受任何参数。

**返回:**该方法返回一个**整数值**，代表一小时中的分钟，范围从 0 到 59。

下面的程序说明了 LocalDateTime.getMinute()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.getMinute() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-03T12:39:10");

        // get MinuteOfHour
        int minuteOfHour = local.getMinute();

        // print result
        System.out.println("MinuteOfHour: "
                           + minuteOfHour);
    }
}
```

**输出:**

```java
MinuteOfHour: 39

```

**程序二:**

```java
// Java program to demonstrate
// LocalDateTime.getMinute() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2019-01-28T22:29:10");

        // get MinuteOfHour
        int minuteOfHour = local.getMinute();

        // print result
        System.out.println("MinuteOfHour: "
                           + minuteOfHour);
    }
}
```

**输出:**

```java
MinuteOfHour: 29

```

参考:[https://docs . Oracle . com/javase/9/docs/API/Java/time/local datetime . html # getMinute–](https://docs.oracle.com/javase/9/docs/api/java/time/LocalDateTime.html#getMinute--)