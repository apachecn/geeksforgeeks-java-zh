# Java 中的 LocalDateTime toLocalDate()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-tolocaldate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-tolocaldate-method-in-java-with-examples/)

**本地日期时间类**的 **toLocalDate()** 方法用于获取该本地日期时间的本地日期表示。此方法从对象类派生而来，其行为方式类似。

**语法:**

```java
public LocalDate toLocalDate()
```

**参数:**该方法不取参数。

**返回:**这个方法返回一个**本地日期值**，它是这个本地日期时间的本地日期表示。

下面的程序说明了 LocalDateTime.toLocalDate()方法:

**程序 1:**

```java
// Program to illustrate the toLocalDate() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime dt = LocalDateTime.now();

        // Get the LocalDate representation of this LocalDateTime
        // using toLocalDate() method
        System.out.println(dt.toLocalDate());
    }
}
```

**输出:**

```java
2018-11-30

```

**程序二:**

```java
// Program to illustrate the toLocalDate() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime dt
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Get the LocalDate representation of this LocalDateTime
        // using toLocalDate() method
        System.out.println(dt.toLocalDate());
    }
}
```

**输出:**

```java
2018-11-03

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/localdatetime . html # tolocaldate()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#toLocalDate())