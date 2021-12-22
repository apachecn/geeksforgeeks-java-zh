# Java 中的 LocalDateTime withYear()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-with year-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-withyear-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的 **withYear()** 方法用于获取该 LocalDateTime 的副本，其中年份被更改为作为参数传递给该方法的年份。该本地日期时间的其余值保持不变。

**语法:**

```java
public LocalDateTime withYear(int year)
```

**参数:**该方法接受一个强制参数**年份**，该参数指定要在结果本地日期时间实例中设置的年份。今年的值可以从最小年到最大年。

**返回:**该函数返回一个**本地日期时间实例**，年份更改为作为参数传递给该方法的年份。该本地日期时间的其余值保持不变。

**异常**:如果年份值无效，函数抛出**日期时间异常**。

下面的程序说明了 LocalDateTime.withYear()方法:

**程序 1:**

```java
// Program to illustrate the withYear() method

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

        // Get a new LocalDateTime with year 1998
        System.out.println("New LocalDateTime: "
                           + dt.withYear(1998));
    }
}
```

**输出:**

```java
Original LocalDateTime: 2018-11-30T10:35:17.833
New LocalDateTime: 1998-11-30T10:35:17.833

```

**程序二:**

```java
// Program to illustrate the withYear() method

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

        // Get a new LocalDateTime with year 20129
        System.out.println("New LocalDateTime: "
                           + dt.withYear(20129));
    }
}
```

**输出:**

```java
Original LocalDateTime: 2015-04-06T10:15:30
New LocalDateTime: +20129-04-06T10:15:30

```

参考:t0[https://docs . Oracle . com/javae/10/docs/API/Java/time/localdatetime . html # withyear(int)]t1]