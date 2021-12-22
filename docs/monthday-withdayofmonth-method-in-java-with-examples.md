# 月日用 Java 中的 DayOfMonth()方法举例

> 原文:[https://www . geesforgeks . org/month day-with dayofmonth-in-Java-method-with-examples/](https://www.geeksforgeeks.org/monthday-withdayofmonth-method-in-java-with-examples/)

**with DayOfMonth(int dayOfMonth)**方法的 **MonthDay** 类用于使用作为参数传递的 dayOfMonth 来更改 MonthDay 对象的月日，然后该方法返回更改后的 MonthDay 的副本。如果在更改操作后，月中某一天的值对于指定月份无效，则会引发异常。

**语法:**

```
public MonthDay withDayOfMonth(int dayOfMonth)

```

**参数:**此方法接受**日**作为参数，该参数是返回月日中要设置的月日，从 1 到 31。

**返回值:**该方法返回基于该月日的月日和请求日。

**异常:**如果月日值无效，或者月日对于该月无效，该方法抛出**日期时间异常**。

以下程序说明了 withDayOfMonth()方法:
**程序 1:**

```
// Java program to demonstrate
// MonthDay.withDayOfMonth() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a MonthDay object
        MonthDay monthday
            = MonthDay.of(8, 28);

        // print instance
        System.out.println("MonthDay before"
                           + " applying method: "
                           + monthday);

        // apply withDayOfMonth method
        // of MonthDay class
        MonthDay updatedlocal
            = monthday.withDayOfMonth(21);

        // print instance
        System.out.println("MonthDay after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
MonthDay before applying method: --08-28
MonthDay after applying method: --08-21

```

**程序 2:**

```
// Java program to demonstrate
// MonthDay.withDayOfMonth() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a MonthDay object
        MonthDay monthday
            = MonthDay.of(10, 31);

        // print instance
        System.out.println("MonthDay before"
                           + " applying method: "
                           + monthday);

        // apply withDayOfMonth method
        // of MonthDay class
        MonthDay updatedlocal
            = monthday.withDayOfMonth(12);

        // print instance
        System.out.println("MonthDay after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
MonthDay before applying method: --10-31
MonthDay after applying method: --10-12

```

**参考文献:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # withDayOfMonth(int)