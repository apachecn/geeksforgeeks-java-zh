# Java 中的 MonthDay now(ZoneId)方法，示例

> 原文:[https://www . geesforgeks . org/month day-now zoneid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-nowzoneid-method-in-java-with-examples/)

Java 中 **MonthDay** 类的 **now(ZoneId zone)** 方法用于从指定时区的系统时钟中获取当前的月-日。

**语法:**

```java
public static MonthDay now(ZoneId zone)
```

**参数:**该方法接受 **ZoneId** 作为参数。

**返回值:**此方法使用系统时钟返回当前**月-日**。

下面的程序说明了 Java 中 MonthDay 的 now(ZoneId zone)方法:

**程序 1:**

```java
// Java program to demonstrate
// MonthDay.now(ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(ZoneId zone) method
        // of MonthDay class
        MonthDay result = MonthDay.now(
            ZoneId.systemDefault());

        // print both month and day
        System.out.println("MonthDay: "
                           + result);
    }
}
```

**输出:**

```java
MonthDay: --05-09

```

**程序二:**

```java
// Java program to demonstrate
// MonthDay.now(ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(ZoneId zone) method
        // of MonthDay class
        MonthDay result = MonthDay.now(
            ZoneId.systemDefault());

        // print only month
        System.out.println("Month: "
                           + result.getMonth());
    }
}
```

**输出:**

```java
Month: MAY

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # now(Java . time . zoneid)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#now(java.time.ZoneId))