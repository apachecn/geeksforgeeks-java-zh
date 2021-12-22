# Java 中的 DayOfWeek getValue()方法，带示例

> 原文:[https://www . geesforgeks . org/dayofweek-getvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dayofweek-getvalue-method-in-java-with-examples/)

**java.time.DayOfWeek** 的 **getValue()** 方法是 java 中的内置函数，返回分配给一周 7 天的整数值，即周一、周二、周三、周四、周五、周六和周日。int 值遵循 ISO-8601 标准，从 1(星期一)到 7(星期日)。

**方法声明:**

```
public int getValue()

```

**语法:**

```
int val = DayOfWeekObject.getValue()

```

**参数:**该方法不接受任何参数。

**返回值:**函数返回一周中某一天的 int 值，例如，1 代表星期一，2 代表星期二，以此类推。

下面程序举例说明上面的方法:
**程序一:**

```
// Java Program Demonstrate getValue()
// method of DayOfWeek
import java.time.*;
import java.time.DayOfWeek;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Set a local date whose day is found
        LocalDate localDate
            = LocalDate.of(1947,
                           Month.AUGUST, 15);

        // Find the day from the local date
        DayOfWeek dayOfWeek
            = DayOfWeek.from(localDate);

        // Printing the day of the week
        // and its Int value
        System.out.println("Day of the Week on"
                           + " 15th August 1947 - "
                           + dayOfWeek.name());

        int val = dayOfWeek.getValue();

        System.out.println("Int Value of "
                           + dayOfWeek.name()
                           + " - " + val);
    }
}
```

**Output:**

```
Day of the Week on 15th August 1947 - FRIDAY
Int Value of FRIDAY - 5

```

**程序 2:**

```
// Java Program Demonstrate getValue()
// method of DayOfWeek
import java.time.*;
import java.time.DayOfWeek;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Set a local date whose day is found
        LocalDate localDate
            = LocalDate.of(2015,
                           Month.JULY, 13);

        // Find the day from the local date
        DayOfWeek dayOfWeek
            = DayOfWeek.from(localDate);

        // Printing the day of the week
        // and its Int value
        System.out.println("Day of the Week on"
                           + " 13th July 2015 - "
                           + dayOfWeek.name());

        int val = dayOfWeek.getValue();

        System.out.println("Int Value of "
                           + dayOfWeek.name()
                           + " - " + val);
    }
}
```

**Output:**

```
Day of the Week on 13th July 2015 - MONDAY
Int Value of MONDAY - 1

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html # getValue–](https://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html#getValue--)