# Java 中的 LocalDateTime plusMinutes()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-plusminutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-plusminutes-method-in-java-with-examples/)

**本地日期时间类**的 **plusMinutes()** 方法用于返回添加了指定分钟数的该日期时间的副本。

**语法** :

```java
public LocalDateTime plusMinutes(long minutes)

```

**参数**:接受单个参数**分钟**，该参数指定了可以为负数的相加分钟数。

**返回值**:该方法根据添加了分钟的日期时间返回**本地日期时间**。

**异常**:程序抛出**日期时间异常**，如果结果超出支持的日期范围，则抛出该异常。

下面的程序说明了 Java 中的 YearMonth.plusMinutes()方法:

**程序 1** :

```java
// Program to illustrate the plusMinutes() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T10:15:30");

        System.out.println("LocalDateTime with 15 minutes added: "
                           + dt1.plusMinutes(15));
    }
}
```

**输出:**

```java
LocalDateTime with 15 minutes added: 2018-01-11T10:30:30

```

**程序二** :

```java
// Program to illustrate the plusMinutes() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T08:15:30");

        System.out.println("LocalDateTime with -2 minutes added: "
                           + dt1.plusMinutes(-2));
    }
}
```

**输出:**

```java
LocalDateTime with -2 minutes added: 2018-01-11T08:13:30

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plusMinutes(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plusMinutes(long))