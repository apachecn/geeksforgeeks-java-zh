# Java 中带有 Second()方法的 LocalDateTime，示例

> 原文:[https://www . geesforgeks . org/local datetime-with second-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-withsecond-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的 **withSecond()** 方法用于获取该 LocalDateTime 的副本，其中秒被更改为秒，并作为参数传递给该方法。该本地日期时间的其余值保持不变。

**语法:**

```java
public LocalDateTime withSecond(int seconds)
```

**参数:**该方法接受单个强制参数**秒**，该参数指定要在结果本地日期时间实例中设置的秒。这个秒的值可以从 0 到 59。

**返回:**该函数返回一个**本地日期时间实例**，将秒更改为秒，作为参数传递给该方法。该本地日期时间的其余值保持不变。

**异常**:如果秒值无效，函数抛出**日期时间异常**。

下面的程序说明了 LocalDateTime.withSecond()方法:

**程序 1:**

```java
// Program to illustrate the withSecond() method

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

        // Get a new LocalDateTime with seconds 0
        System.out.println("New LocalDateTime: "
                           + dt.withSecond(0));
    }
}
```

**输出:**

```java
Original LocalDateTime: 2018-11-30T10:39:52.924
New LocalDateTime: 2018-11-30T10:39:00.924

```

**程序二:**

```java
// Program to illustrate the withSecond() method

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

        // Get a new LocalDateTime with seconds 59
        System.out.println("New LocalDateTime: "
                           + dt.withSecond(59));
    }
}
```

**输出:**

```java
Original LocalDateTime: 2015-04-06T10:15:30
New LocalDateTime: 2015-04-06T10:15:59

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # with second(int)