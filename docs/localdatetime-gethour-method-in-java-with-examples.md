# Java 中的 LocalDateTime getHour()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-get hour-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-gethour-method-in-java-with-examples/)

**本地日期时间类**的 **getHour()** 方法用于返回一天中的小时字段。此方法返回一个 0 到 23 之间的整数值，即一天中的小时数。

**语法:**

```java
public int getHour()

```

**参数:**此方法不接受任何参数。

**返回:**该方法返回一个**整数值**，代表一天中的小时，范围从 0 到 23。

下面的程序说明了 LocalDateTime.getHour()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.getHour() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-03T12:39:10");

        // get HourOfDay
        int hourOfDay = local.getHour();

        // print result
        System.out.println("HourOfDay: "
                           + hourOfDay);
    }
}
```

**输出:**

```java
HourOfDay: 12

```

**程序二:**

```java
// Java program to demonstrate
// LocalDateTime.getHour() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2019-01-28T22:29:10");

        // get HourOfDay
        int hourOfDay = local.getHour();

        // print result
        System.out.println("HourOfDay: "
                           + hourOfDay);
    }
}
```

**输出:**

```java
HourOfDay: 22

```

参考:t0[https://docs . Oracle . com/javae/9/docs/API/Java/time/localdatetime . html # get hour]-t1]