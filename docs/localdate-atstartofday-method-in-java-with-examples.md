# Java 中的 LocalDate atStartOfDay()方法，示例

> 原文:[https://www . geesforgeks . org/local date-at startofday-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-atstartofday-method-in-java-with-examples/)

Java 中 LocalDate 类的 atStartOfDay()方法是将这个日期和午夜的时间结合起来，在这个日期的开始创建一个 LocalDateTime。

**语法** :

```java
public ZonedDateTime atStartOfDay(ZoneId zone)

```

**参数**:该方法接受一个参数*区域*，该参数是要使用的区域标识，不需要为空。该参数不是必需的。

**返回值**:返回该日期开始时午夜的本地日期时间，不为空。

下面的程序说明了 Java 中 LocalDate 的 atStartOfDay()方法:

**程序 1** :

```java
// Program to illustrate the atStartOfDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // parses the local date
        LocalDate dt = LocalDate.parse("2019-11-01");
        System.out.println(dt);

        // Function call
        LocalDateTime dt1 = dt.atStartOfDay();
        System.out.println(dt1);
    }
}
```

**输出:**

```java
2019-11-01
2019-11-01T00:00

```

**程序 2** :带参数的程序。

```java
// Program to illustrate the atStartOfDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // parses the local date
        LocalDate dt = LocalDate.parse("2018-01-20");
        System.out.println(dt);

        // Function call
        ZonedDateTime dt1 = dt.atStartOfDay(ZoneId.systemDefault());
        System.out.println(dt1);
    }
}
```

**输出:**

```java
2018-01-20
2018-01-20T00:00Z[Etc/UTC]

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # at startofday()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#atStartOfDay())