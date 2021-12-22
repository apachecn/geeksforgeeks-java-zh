# Java 中的 LocalDateTime toLocalTime()方法，带示例

> 原文:[https://www . geeksforgeeks . org/local datetime-tolocaltime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-tolocaltime-method-in-java-with-examples/)

**LocalDateTime 类**的 **toLocalTime()** 方法用于获取该 LocalDateTime 的 LocalTime 表示。此方法从对象类派生而来，其行为方式类似。

**语法:**

```java
public LocalTime toLocalTime()
```

**参数:**该方法不取参数。

**返回:**这个方法返回一个**本地时间值**，它是这个本地日期时间的本地时间表示。

下面的程序说明了 LocalDateTime.toLocalTime()方法:

**程序 1:**

```java
// Program to illustrate the toLocalTime() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime dt = LocalDateTime.now();

        // Get the LocalTime representation of this LocalDateTime
        // using toLocalTime() method
        System.out.println(dt.toLocalTime());
    }
}
```

**输出:**

```java
10:20:00.280

```

**程序二:**

```java
// Program to illustrate the toLocalTime() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime dt
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Get the LocalTime representation of this LocalDateTime
        // using toLocalTime() method
        System.out.println(dt.toLocalTime());
    }
}
```

**输出:**

```java
12:45:30

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/localdatetime . html # tolocaltime()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#toLocalTime())