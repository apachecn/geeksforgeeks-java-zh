# Java 中的 LocalDateTime withMonth()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-with month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-withmonth-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的 **withMonth()** 方法用于获取该 LocalDateTime 的副本，其中月份被更改为作为参数传递给该方法的月份。该本地日期时间的其余值保持不变。

**语法:**

```java
public LocalDateTime withMonth(int months)
```

**参数:**此方法接受单个强制参数**月份**，该参数指定了要在结果 LocalDateTime 实例中设置的月份。这个月的值可以从 1 到 12。

**返回:**函数返回一个**本地日期时间实例**，将月份改为月份作为参数传递给该方法。该本地日期时间的其余值保持不变。

**异常**:如果月份值无效，函数抛出**日期时间异常**。

下面的程序说明了 LocalDateTime.withMonth()方法:

**程序 1:**

```java
// Program to illustrate the withMonth() method

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

        // Get a new LocalDateTime with months 5
        System.out.println("New LocalDateTime: "
                           + dt.withMonth(5));
    }
}
```

**输出:**

```java
Original LocalDateTime: 2018-11-30T12:51:39.472
New LocalDateTime: 2018-05-30T12:51:39.472

```

**程序二:**

```java
// Program to illustrate the withMonth() method

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

        // Get a new LocalDateTime with months 12
        System.out.println("New LocalDateTime: "
                           + dt.withMonth(12));
    }
}
```

**输出:**

```java
Original LocalDateTime: 2015-04-06T10:15:30
New LocalDateTime: 2015-12-06T10:15:30

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # with month(int)