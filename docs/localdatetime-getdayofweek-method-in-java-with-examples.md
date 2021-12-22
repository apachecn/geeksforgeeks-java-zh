# Java 中的 LocalDateTime getDayOfWeek()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-getdayofweek-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-getdayofweek-method-in-java-with-examples/)

LocalDateTime 类的 **getDayOfWeek()** 方法用于返回星期几字段，这是一个枚举 DayOfWeek。此方法返回一周中某一天的枚举 DayOfWeek。

**语法:**

```
public DayOfWeek getDayOfWeek()

```

**参数:**该方法不接受任何参数。

**返回:**该方法从枚举 DayOfWeek 返回**星期几**。

下面的程序说明了 LocalDateTime.getDayOfWeek()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.getDayOfWeek() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-03T12:39:10");

        // get dayofweek for this LocalDateTime
        DayOfWeek dayofweek
            = local.getDayOfWeek();

        // print result
        System.out.println("Day of Week: "
                           + dayofweek);
    }
}
```

**输出:**

```
Day of Week: MONDAY

```

**程序二:**

```
// Java program to demonstrate
// LocalDateTime.getDayOfWeek() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-29T02:39:10");

        // get dayofweek for this LocalDateTime
        DayOfWeek dayofweek = local.getDayOfWeek();

        // print result
        System.out.println("Day of Week: "
                           + dayofweek);
    }
}
```

**输出:**

```
Day of Week: SATURDAY

```

参考:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # getDayOfWeek()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#getDayOfWeek())