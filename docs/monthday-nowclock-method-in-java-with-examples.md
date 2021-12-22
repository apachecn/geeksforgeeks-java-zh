# Java 中的 MonthDay now(Clock)方法，示例

> 原文:[https://www . geesforgeks . org/month day-now clock-in-Java-method-with-examples/](https://www.geeksforgeeks.org/monthday-nowclock-method-in-java-with-examples/)

Java 中 **MonthDay** 类的 **now(Clock clock)** 方法用于从指定的时钟获取当前的月-日。

**语法:**

```
public static MonthDay now(Clock clock)
```

**参数:**此方法接受**时钟**作为代表要使用的时钟的参数。

**返回值:**此方法返回当前**月-日**。

下面的程序说明了 Java 中 MonthDay 的 now(时钟)方法:

**程序 1:**

```
// Java program to demonstrate
// MonthDay.now(Clock clock) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(Clock clock) method
        // of MonthDay class
        MonthDay result = MonthDay.now(
            Clock.systemUTC());

        // print both month and day
        System.out.println("MonthDay: "
                           + result);
    }
}
```

**输出:**

```
MonthDay: --05-09

```

**程序二:**

```
// Java program to demonstrate
// MonthDay.now(Clock clock) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(Clock clock) method
        // of MonthDay class
        MonthDay result = MonthDay.now(
            Clock.systemUTC());

        // print only month
        System.out.println("Month: "
                           + result.getMonth());
    }
}
```

**输出:**

```
Month: MAY

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # now(Java . time . clock)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#now(java.time.Clock))