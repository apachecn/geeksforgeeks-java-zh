# Java 中的 LocalTime now(时钟)方法，示例

> 原文:[https://www . geesforgeks . org/local time-now clock-in-Java-method-with-examples/](https://www.geeksforgeeks.org/localtime-nowclock-method-in-java-with-examples/)

Java 中 **LocalTime** 类的 **now(Clock clock)** 方法用于从指定的时钟获取当前时间。

**语法:**

```
public static LocalTime now(
    Clock clock)
```

**参数:**此方法接受**时钟**作为代表要使用的时钟的参数。

**返回值:**此方法返回当前**时间**。

下面的程序说明了 Java 中 LocalTime 的 now(时钟)方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.now(Clock clock) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(Clock clock) method
        // of LocalTime class
        LocalTime time = LocalTime.now(
            Clock.systemUTC());

        // print time
        System.out.println("Time: "
                           + time);
    }
}
```

**输出:**

```
Time: 21:04:28.811

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.now(Clock clock) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(Clock clock) method
        // of LocalTime class
        LocalTime time = LocalTime.now(
            Clock.systemUTC());

        // print time
        System.out.println("Time: "
                           + time);
    }
}
```

**输出:**

```
Time: 21:05:21.192

```

以上两个例子说明了同一程序按时间顺序的结果差异。

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # now(Java . time . clock)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#now(java.time.Clock))