# 月初一日 Java 中的 DayOfYear()方法

> 原文:[https://www . geesforgeks . org/month-first dayofyear-in-method-Java/](https://www.geeksforgeeks.org/month-firstdayofyear-method-in-java/)

**firstDayOfYear()** 是一种内置的 Month ENUM 方法，用于获取本月第一天对应的一年中的某一天。

**语法** :

```
public int firstDayOfYear(boolean leapYear)

```

**参数**:该方法接受单个参数 *leapYear* ，这是一个布尔标志变量，表示今年是否是闰年。

**返回值**:此方法返回本月初一对应的年月日。

下面的程序说明了上述方法:

**程序 1** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.Temporal;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Set the month to february
        Month month = Month.of(2);

        // Get corresponding day-of-year of the
        // first day of february in a non-leap year
        System.out.println(month.firstDayOfYear(false));
    }
}
```

**输出:**

```
32

```

**程序二** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.Temporal;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Set the month to february
        Month month = Month.of(3);

        // Get corresponding day-of-year of the
        // first day of March in a leap year
        System.out.println(month.firstDayOfYear(true));
    }
}
```

**输出:**

```
61

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # first day fyear-boolean-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#firstDayOfYear-boolean-)