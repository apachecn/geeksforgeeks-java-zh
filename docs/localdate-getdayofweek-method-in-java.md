# Java 中的 LocalDate getDayOfWeek()方法

> 原文:[https://www . geesforgeks . org/local date-getdayofweek-method-in-Java/](https://www.geeksforgeeks.org/localdate-getdayofweek-method-in-java/)

Java 中 LocalDate 类的 getDayOfWeek()方法获取星期几字段，这是一个枚举 DayOfWeek。

**语法** :

```java
public DayOfWeek getDayOfWeek()

```

**参数**:该方法不接受任何参数。

**返回值**:函数返回星期几，不为空。

下面的程序说明了 Java 中 LocalDate 的 **getDayOfWeek()** 方法:

**程序 1** :

```java
// Program to illustrate the getDayOfWeek() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the day
        System.out.println(dt.getDayOfWeek());
    }
}
```

**输出:**

```java
TUESDAY

```

**程序二** :

```java
// Program to illustrate the getDayOfWeek() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-01-09");

        // Prints the day
        System.out.println(dt.getDayOfWeek());
    }
}
```

**输出:**

```java
TUESDAY

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # getDayOfWeek()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getDayOfWeek())