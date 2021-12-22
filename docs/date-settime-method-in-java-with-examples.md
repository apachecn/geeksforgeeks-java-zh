# Java 中的 Date setTime()方法，示例

> 原文:[https://www . geesforgeks . org/date-set time-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-settime-method-in-java-with-examples/)

**Java Date 类**的 **setTime()** 方法设置日期对象。它将 date 对象设置为表示 1970 年 1 月 1 日 00:00:00 GMT 之后的时间毫秒。
**语法:**

```
public void setTime(long time)

```

**参数:**函数接受单个参数**时间**，指定毫秒数。

**返回值:** It 方法没有返回值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```
// Java code to demonstrate
// setTime() function of Date class

import java.util.Date;
import java.util.Calendar;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a date object with specified time.
        Date dateOne = new Date();

        System.out.println("Date initially: "
                           + dateOne);

        // Sets the time
        dateOne.setTime(1000);

        // Prints the time
        System.out.println("Date after setting"
                           + " the time: "
                           + dateOne);
    }
}
```

**Output:**

```
Date initially: Wed Jan 02 09:34:03 UTC 2019
Date after setting the time: Thu Jan 01 00:00:01 UTC 1970

```

**程序 2:**

```
// Java code to demonstrate
// setTime() function of Date class

import java.util.Date;
import java.util.Calendar;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 11);

        // set Date
        c1.set(Calendar.DATE, 05);

        // set Year
        c1.set(Calendar.YEAR, 1996);

        // creating a date object with specified time.
        Date dateOne = c1.getTime();

        System.out.println("Date initially: "
                           + dateOne);

        // Sets the time
        dateOne.setTime(1000999);

        // Prints the time
        System.out.println("Date after setting"
                           + " the time: "
                           + dateOne);
    }
}
```

**Output:**

```
Date initially: Thu Dec 05 09:32:53 UTC 1996
Date after setting the time: Thu Jan 01 00:16:40 UTC 1970

```