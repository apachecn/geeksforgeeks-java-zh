# Java 中的 LocalDateTime plusDays()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-plus days-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-plusdays-method-in-java-with-examples/)

**LocalDateTime 类**的 **plusDays()** 方法用于返回添加了指定天数的该日期时间的副本。

**语法** :

```java
public LocalDateTime plusDays(long days)

```

**参数**:接受单个参数**天数**，指定要添加的天数，可以是负数。

**返回值**:该方法根据添加了天数的日期时间返回**本地日期时间**。

**异常**:程序抛出**日期时间异常**，如果结果超出支持的天数范围，则抛出该异常。

下面的程序说明了 Java 中的 YearMonth.plusDays()方法:

**程序 1** :

```java
// Program to illustrate the plusDays() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T10:15:30");

        System.out.println("LocalDateTime with 15 days added: "
                           + dt1.plusDays(15));
    }
}
```

**输出:**

```java
LocalDateTime with 15 days added: 2018-01-26T10:15:30

```

**程序二** :

```java
// Program to illustrate the plusDays() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T08:15:30");

        System.out.println("LocalDateTime with -2 days added: "
                           + dt1.plusDays(-2));
    }
}
```

**输出:**

```java
LocalDateTime with -2 days added: 2018-01-09T08:15:30

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plusDays(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plusDays(long))