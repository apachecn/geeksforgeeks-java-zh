# 带有示例的 Java 中的 Hour()方法的本地日期时间

> 原文:[https://www . geesforgeks . org/local datetime-with our-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-withhour-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的**withour()**方法用于获取该 LocalDateTime 的副本，其中小时被更改为小时，并作为参数传递给该方法。该本地日期时间的其余值保持不变。

**语法:**

```java
public LocalDateTime withHour(int hours)
```

**参数:**此方法接受单个强制参数**小时数**，该参数指定要在结果本地日期时间实例中设置的小时数。这个小时的值可以从 0 到 23。

**返回:**该函数返回一个**本地日期时间实例**，将小时数改为小时数作为参数传递给该方法。该本地日期时间的其余值保持不变。

**异常**:如果小时值无效，该函数将抛出**日期时间异常**。

下面的程序说明了 LocalDateTime.withHour()方法:

**程序 1:**

```java
// Program to illustrate the withHour() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Get the LocalDateTime instance
        LocalDateTime dt = LocalDateTime.now();

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + dt.toString());

        // Get a new LocalDateTime with hours 0
        System.out.println("New LocalDateTime: "
                           + dt.withHour(0));
    }
}
```

**输出:**

```java
Original LocalDateTime: 2018-11-30T12:53:06.591
New LocalDateTime: 2018-11-30T00:53:06.591

```

**程序二:**

```java
// Program to illustrate the withHour() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Get the LocalDateTime instance
        LocalDateTime dt
            = LocalDateTime
                  .parse("2015-04-06T10:15:30");

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + dt.toString());

        // Get a new LocalDateTime with hours 20
        System.out.println("New LocalDateTime: "
                           + dt.withHour(20));
    }
}
```

**输出:**

```java
Original LocalDateTime: 2015-04-06T10:15:30
New LocalDateTime: 2015-04-06T20:15:30

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # withour(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#withHour(int))