# 带示例的 Java 中的 MonthDay withMonth()方法

> 原文:[https://www . geesforgeks . org/month day-with month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-withmonth-method-in-java-with-examples/)

**withMonth(int month)** 方法的 **MonthDay** 类，用于使用作为参数传递的 MonthDay 更改 MonthDay 对象的年中月份，然后该方法返回更改后的 MonthDay 的副本。如果某月某日对于指定月份无效，则该日将被调整为该月的最后一个有效日期。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public MonthDay withMonth(int month)

```

**参数:**该方法接受**月**作为参数，该参数是返回的月日中设置的月份，从 1 月 1 日到 12 月 12 日。

**返回值:**该方法返回一个月日，该月日基于该月日与请求的月份。

**异常:**如果年月值无效，该方法抛出**日期时间异常**。

下面的程序说明了 withMonth()方法:
**程序 1:**

```
// Java program to demonstrate
// MonthDay.withMonth() method

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

        // apply withMonth method of MonthDay class
        MonthDay updatedlocal = monthday.withMonth(1);

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
MonthDay after applying method: --01-28

```

**程序 2:**

```
// Java program to demonstrate
// MonthDay.withMonth() method

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

        // apply withMonth method of MonthDay class
        MonthDay updatedlocal = monthday.withMonth(5);

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
MonthDay after applying method: --05-31

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # with month(int)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#withMonth(int))