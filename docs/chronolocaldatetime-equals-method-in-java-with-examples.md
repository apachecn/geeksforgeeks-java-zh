# Java 中的 ChronoLocalDateTime 等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-equals-method-in-java-with-examples/)

Java 方法中**ChronalDatetime**接口的 **equals()** 方法检查该日期是否等于另一个日期，包括年表。

**语法** :

```java
boolean equals(Object other)

```

**参数**:此方法接受一个参数 ***【其他】*** ，指定要比较的其他日期。

**返回值**:返回一个**布尔值**，如果两者相等则为真，否则返回假。此外，如果参数为 null，它将返回 false。

下面的程序说明了 Java 中的 ChronoLocalDateTime 的 equals()方法:

**程序 1** :

```java
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDateTime dt
            = LocalDateTime.parse("2018-12-06T19:21:12");

        System.out.println(dt);

        // Second date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-12-06T19:21:12");

        System.out.println(dt1);

        // Compare both dates
        System.out.println(dt1.equals(dt));
    }
}
```

**输出:**

```java
2018-12-06T19:21:12
2018-12-06T19:21:12
true

```

**程序二** :

```java
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDateTime dt
            = LocalDateTime.parse("2018-12-05T19:21:12");
        System.out.println(dt);

        // Second date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-12-06T19:21:12");
        System.out.println(dt1);

        // Compare both dates
        System.out.println(dt1.equals(dt));
    }
}
```

**输出:**

```java
2018-12-05T19:21:12
2018-12-06T19:21:12
false

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#equals-java.lang.Object-)