# 通过滚动小时和月来显示时间的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-按小时和月滚动节目到节目的时间/](https://www.geeksforgeeks.org/java-program-to-show-time-by-rolling-through-hours-and-months/)

[Java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包有一个 [Calendar](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/) 类，里面有一些预定义的方法，帮助我们做一些和日期时间相关的操作。日历类有一个预定义的方法叫做 [roll()](https://www.geeksforgeeks.org/calendar-roll-method-in-java-with-examples/) 方法，在这个方法的帮助下，我们可以滚动月份(不改变年份)和小时(不改变月份和年份)。

**滚动**基本上是指经过一定时间后恢复到原来的状态。举个例子，我们假设现在是 10 月份，我们已经将这个月滚动了 50 个月，这意味着我们已经滚动了 2 个月，即(50%12=2)，因为一年总共有 12 个月，所以滚动了 50 个月之后的当前月份将是 12 月。

考虑另一个例子，假设我们已经将小时数滚动了 76，并且时间的当前状态是下午 5:00，日期是 2020 年 10 月 22 日，因此在我们滚动了 76 小时后，时间的状态将是晚上 9:00，数据将是 2020 年 10 月 22 日，之所以如此，是因为一天中总共有 24 个小时，并且(76%24=4)，因此当前时间状态只会增加 4。

**语法:**

```
public abstract void roll(int calendar_field, boolean up_down)
```

这里， **roll()** 法取 2 个参数**历 _ 场**和**上 _ 下**。

*   **日历 _ 字段** : 它是我们要滚动的小时或月或年
*   **up_down** :就是我们要滚动的量，可以是布尔值，也可以是整数值。在上面的例子中，展示了如何滚动一个整数值(可以是正值也可以是负值)，但是对于一个布尔值，如果传递的值为真，则意味着我们必须滚动 **+1** 的金额，如果传递的值为假，则意味着滚动 **-1** 的金额。

**示例:**下面的示例说明了如何以编程方式使用 roll()方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show how to roll through
// hours or years or months using roll() method
import java.util.Calendar;
import java.util.Date;

public class CalendarExample1 {
    public static void main(String[] args) throws Exception
    {
        // getting the current date
        Date d1 = new Date();

          // create two calendar instances
        Calendar c1 = Calendar.getInstance();
        Calendar c2 = Calendar.getInstance();

        // setting the current date and time in calendar
        c1.setTime(d1);
        c2.setTime(d1);

          // print the current date
        System.out.println("Today is " + d1.toString());

        // rolling over month by 50
        c1.roll(Calendar.MONTH, 50);
        System.out.println(
            "Date after rolling by 50 over  month will be "
            + c1.getTime().toString());

        // rolling over hour by 70
        c1.roll(Calendar.HOUR, 70);
        System.out.println(
            "Date after rolling by 70 over hours will be "
            + c1.getTime().toString());

        // rolling over year by 2
        c1.roll(Calendar.YEAR, 2);
        System.out.println(
            "Date after  rolling by 2 over year is "
            + c1.getTime().toString());

        // false rolling over month
        c2.roll(Calendar.MONTH, false);
        System.out.println(
            "Date after false rolling over month will be "
            + c2.getTime().toString());

        // true rolling over hour
        c2.roll(Calendar.HOUR, true);
        System.out.println(
            "Date after true rolling over hour will be "
            + c2.getTime().toString());

        // true rolling over year
        c2.roll(Calendar.YEAR, true);
        System.out.println(
            "Date after true rolling over year is "
            + c2.getTime().toString());
    }
}
```

**Output**

```
Today is Fri Oct 30 06:19:15 UTC 2020
Date after rolling by 50 over  month will be Wed Dec 30 06:19:15 UTC 2020
Date after rolling by 70 over hours will be Wed Dec 30 04:19:15 UTC 2020
Date after  rolling by 2 over year is Fri Dec 30 04:19:15 UTC 2022
Date after false rolling over month will be Wed Sep 30 06:19:15 UTC 2020
Date after true rolling over hour will be Wed Sep 30 07:19:15 UTC 2020
Date after true rolling over year is Thu Sep 30 07:19:15 UTC 2021
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// roll() method

import java.util.*;

public class CalendarExample2 {
    public static void main(String args[])
    {
        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Displaying the month
        System.out.println("The Current Month"
                           + " is: "
                           + calndr.get(Calendar.MONTH));

        // Incrementing the month
        // true indicates addition
        calndr.roll(Calendar.MONTH, true);

        // Displaying the result after operation
        System.out.println("The New Month is: "
                           + calndr.get(Calendar.MONTH));

        // Decrementing the month
        // false indicates subtraction
        calndr.roll(Calendar.MONTH, false);

        // Displaying the result after operation
        System.out.println("The new month is: "
                           + calndr.get(Calendar.MONTH));
    }
}
```

**Output**

```
The Current Month is: 9
The New Month is: 10
The new month is: 9
```