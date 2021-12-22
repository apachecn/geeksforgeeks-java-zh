# Java 中的 Month firstMonthOfQuarter()方法

> 原文:[https://www . geesforgeks . org/month-first monthofquart-in-method-in-Java/](https://www.geeksforgeeks.org/month-firstmonthofquarter-method-in-java/)

**firstMonthOfQuarter()** 是一种内置的 Month ENUM 方法，用于获取本季度对应的第一个月。季度的定义是将一年分为 4 组:

*   Group 1: January, February and March
*   Group 2: April, May and June
*   Group 3: July, August and September
*   Group 4: October, November and December

**语法** :

```
public int firstMonthOfQuarter()

```

**参数**:该方法不接受任何参数。

**返回值**:此方法返回本季度第一个月对应的月份。

下面的程序说明了上述方法:

**程序 1** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.Temporal;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Set the month to february, 1st Quarter
        Month month = Month.of(2);

        // Get the first month of this quarter
        System.out.println(month.firstMonthOfQuarter());
    }
}
```

**输出:**

```
JANUARY

```

**程序二** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.Temporal;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Set the month to JUNE, 2nd Quarter
        Month month = Month.of(6);

        // Get the first month of this quarter
        System.out.println(month.firstMonthOfQuarter());
    }
}
```

**输出:**

```
APRIL

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # first monthofquarter–](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#firstMonthOfQuarter--)