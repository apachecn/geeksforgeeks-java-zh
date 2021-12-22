# Java 中(月，int)方法的月日，示例

> 原文:[https://www . geesforgeks . org/month day-of month-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-ofmonth-int-method-in-java-with-examples/)

Java 中 **MonthDay** 类的**(月月，int day fmonth)**方法用于获取 **MonthDay** 的实例。
**语法:**

```
public static MonthDay of(
    Month month, int dayOfMonth)
```

**参数:**该方法接受两个参数:

*   **月**:代表一年中的月份。
*   **dayOfMonth** :表示一个月中的某一天。

**返回值:**此方法返回**月-日**。

**异常:**如果任何字段的值超出范围或该月的某一天对该月无效，该方法将抛出**日期时间异常**。

下面的程序说明了 Java 中 MonthDay 的(月，国际日)方法:

**程序 1:**

```
// Java program to demonstrate
// MonthDay.of(Month month, int dayOfMonth) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply of(Month month, int dayOfMonth) method
        // of MonthDay class
        MonthDay monthday = MonthDay.of(Month.MAY, 9);

        // print both month and day
        System.out.println("MonthDay: "
                           + monthday);
    }
}
```

**Output:**

```
MonthDay: --05-09

```

**程序 2:**

```
// Java program to demonstrate
// MonthDay.of(Month month, int dayOfMonth) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply of(Month month, int dayOfMonth) method
        // of MonthDay class
        MonthDay monthday = MonthDay.of(Month.MAY, 9);

        // print only month
        System.out.println("Month: "
                           + monthday.getMonth());
    }
}
```

**Output:**

```
Month: MAY

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # of(Java . time . month，int)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#of(java.time.Month, int))