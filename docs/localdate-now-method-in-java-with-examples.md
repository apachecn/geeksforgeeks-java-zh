# Java 中的 LocalDate now()方法，示例

> 原文:[https://www . geesforgeks . org/local date-now-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-now-method-in-java-with-examples/)

在 LocalDate 类中，根据传递给它的参数，有三种 now()方法。

### 现在()

**now()** 一个 **LocalDate** 类的方法，用于从默认时区的系统时钟中获取当前日期。此方法将根据系统时钟和默认时区返回本地日期，以获取当前日期。

**语法:**

```java
public static LocalDate now()

```

**参数:**该方法不接受参数。

**返回值:**该方法使用系统时钟和默认时区返回当前日期。

下面的程序说明了 now()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDate.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an LocalDate object
        LocalDate lt
            = LocalDate.now();

        // print result
        System.out.println("LocalDate : "
                           + lt);
    }
}
```

**Output:**

```java
LocalDate : 2019-01-21

```

### 现在(时钟)

**now(Clock clock)** 一个 **LocalDate** 类的方法，用于根据作为参数传递的指定时钟返回当前日期。

**语法:**

```java
public static LocalDate now(Clock clock)

```

**参数:**该方法接受**时钟**作为参数，该参数是要使用的时钟。

**返回值:**此方法返回**当前日期**。

下面的程序说明了 now()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDate.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a clock
        Clock cl = Clock.systemUTC();

        // create an LocalDate object using now(Clock)
        LocalDate lt
            = LocalDate.now(cl);

        // print result
        System.out.println("LocalDate : "
                           + lt);
    }
}
```

**Output:**

```java
LocalDate : 2019-01-21

```

### 现在(区域标识区域)

**now(ZoneId zone)** 一个 **LocalDate** 类的方法，用于从指定时区的系统时钟返回作为参数传递的当前日期。指定时区避免了对默认时区的依赖。

**语法:**

```java
public static LocalDate now(ZoneId zone)

```

**参数:**该方法接受**区域**作为参数，该参数是要使用的区域。

**返回值:**此方法返回**当前日期时间**。

下面的程序说明了 now()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDate.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a clock
        ZoneId zid = ZoneId.of("Europe/Paris");

        // create an LocalDate object using now(zoneId)
        LocalDate lt
            = LocalDate.now(zid);

        // print result
        System.out.println("LocalDate : "
                           + lt);
    }
}
```

**Output:**

```java
LocalDate : 2019-01-21

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # now()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#now())
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # now(Java . time . clock)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#now(java.time.Clock))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html。](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#now(java.time.ZoneId))