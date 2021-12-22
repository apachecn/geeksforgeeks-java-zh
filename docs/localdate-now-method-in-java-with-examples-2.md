# Java 中的 LocalDate now()方法，示例

> 原文:[https://www . geesforgeks . org/local date-now-method-in-Java-with-examples-2/](https://www.geeksforgeeks.org/localdate-now-method-in-java-with-examples-2/)

在 LocalTime 类中，根据传递给它的参数，有三种 now()方法。

### 现在()

**now()** 一个 **LocalTime** 类的方法，用于从默认时区的系统时钟中获取当前时间。此方法将根据系统时钟和默认时区返回本地时间，以获取当前时间。

**语法:**

```
public static LocalTime now()

```

**参数:**该方法不接受参数。

**返回值:**此方法使用系统时钟返回当前时间。

下面的程序说明了 now()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalTime.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an LocalTime object
        LocalTime lt
            = LocalTime.now();

        // print result
        System.out.println("LocalTime : "
                           + lt);
    }
}
```

**Output:**

```
LocalTime : 05:47:38.946

```

### 现在(时钟)

**now(Clock clock)** 一个 **LocalTime** 类的方法，用于根据作为参数传递的指定时钟返回当前时间。

**语法:**

```
public static LocalTime now(Clock clock)

```

**参数:**该方法接受**时钟**作为参数，该参数是要使用的时钟。

**返回值:**此方法返回**当前时间**。

下面的程序说明了 now()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalTime.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a clock
        Clock cl = Clock.systemUTC();

        // create an LocalTime object using now(Clock)
        LocalTime lt
            = LocalTime.now(cl);

        // print result
        System.out.println("LocalTime : "
                           + lt);
    }
}
```

**Output:**

```
LocalTime : 05:47:44.184

```

### 现在(区域标识区域)

**now(ZoneId zone)** 一个 **LocalTime** 类的方法，用于从指定时区的系统时钟返回作为参数传递的当前时间。指定时区避免了对默认时区的依赖。

**语法:**

```
public static LocalTime now(ZoneId zone)

```

**参数:**该方法接受**区域**作为参数，该参数是要使用的区域。

**返回值:**此方法返回**当前时间**。

下面的程序说明了 now()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalTime.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a clock
        ZoneId zid = ZoneId.of("Europe/Paris");

        // create an LocalTime object using now(zoneId)
        LocalTime lt
            = LocalTime.now(zid);

        // print result
        System.out.println("LocalTime : "
                           + lt);
    }
}
```

**Output:**

```
LocalTime : 06:47:45.982

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # now()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#now())
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # now(Java . time . clock)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#now(java.time.Clock))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . HTT](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#now(java.time.ZoneId))