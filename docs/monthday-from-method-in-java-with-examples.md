# Java 中的 MonthDay from()方法，带示例

> 原文:[https://www . geesforgeks . org/monthday-from-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-from-method-in-java-with-examples/)

Java 中 **MonthDay 类**的 **from()** 方法从时态对象中获取 MonthDay 的一个实例。

**语法:**

```
public static MonthDay from(TemporalAccessor temporal)
```

**参数:**该方法接受一个参数**时态**，指定要转换的时态对象，该参数不为空。

**返回:**函数返回本地日期，不为空。

**异常**:如果无法转换为月日，函数抛出**日期时间异常**。

以下程序说明了**月日从()**方法:

**程序 1:**

```
// Program to illustrate the from() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        MonthDay date 
= MonthDay.from(ZonedDateTime.now());

        System.out.println(date);
    }
}
```

**输出:**

```
--12-06

```

**程序二:**

```
// Program to illustrate the from() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        MonthDay date = MonthDay.from(ZonedDateTime.now());
        System.out.println(date);
    }
}
```

**输出:**

```
--12-06

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/monthday . html # from-Java . time . temporal accessor-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#from-java.time.temporal.TemporalAccessor-)