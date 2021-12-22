# Java 中的 LocalDateTime withMinute()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-with minute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-withminute-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的 **withMinute()** 方法用于获取该 LocalDateTime 的副本，其中分钟被更改为作为参数传递给该方法的分钟。该本地日期时间的其余值保持不变。

**语法:**

```
public LocalDateTime withMinute(int minutes)
```

**参数:**此方法接受单个强制参数**分钟**，该参数指定要在结果本地日期时间实例中设置的分钟数。该分钟值的范围可以从 0 到 59。

**返回:**该函数返回一个**本地日期时间实例**，其中分钟被更改为作为参数传递给该方法的分钟。该本地日期时间的其余值保持不变。

**异常**:如果分钟值无效，该函数抛出**日期时间异常**。

下面的程序说明了 LocalDateTime.withMinute()方法:

**程序 1:**

```
// Program to illustrate the withMinute() method

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

        // Get a new LocalDateTime with minutes 0
        System.out.println("New LocalDateTime: "
                           + dt.withMinute(0));
    }
}
```

**输出:**

```
Original LocalDateTime: 2018-11-30T12:52:26.105
New LocalDateTime: 2018-11-30T12:00:26.105

```

**程序二:**

```
// Program to illustrate the withMinute() method

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

        // Get a new LocalDateTime with minutes 59
        System.out.println("New LocalDateTime: "
                           + dt.withMinute(59));
    }
}
```

**输出:**

```
Original LocalDateTime: 2015-04-06T10:15:30
New LocalDateTime: 2015-04-06T10:59:30

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # with minute(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#withMinute(int))