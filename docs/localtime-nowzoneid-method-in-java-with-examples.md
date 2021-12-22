# Java 中的 LocalTime now(ZoneId)方法，示例

> 原文:[https://www . geesforgeks . org/local time-now zoneid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-nowzoneid-method-in-java-with-examples/)

Java 中 **LocalTime** 类的 **now(ZoneId zone)** 方法用于从指定时区的系统时钟中获取当前时间。

**语法:**

```java
public static LocalTime now(ZoneId zone)
```

**参数:**该方法接受 **ZoneId** 作为参数。

**返回值:**该方法使用系统时钟返回当前**时间**。

下面的程序说明了 Java 中 LocalTime 的 now(ZoneId zone)方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.now(ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(ZoneId zone) method
        // of LocalTime class
        LocalTime time = LocalTime.now(
            ZoneId.systemDefault());

        // print time
        System.out.println("Time: "
                           + time);
    }
}
```

**输出:**

```java
Time: 20:57:30.035

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.now(ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(ZoneId zone) method
        // of LocalTime class
        LocalTime time = LocalTime.now(
            ZoneId.systemDefault());

        // print time
        System.out.println("Time: "
                           + time);
    }
}
```

**输出:**

```java
Time: 20:57:50.318

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # now(Java . time . zoneid)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#now(java.time.ZoneId))