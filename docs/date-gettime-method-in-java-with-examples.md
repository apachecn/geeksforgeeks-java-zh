# Java 中的 Date getTime()方法，带示例

> 原文:[https://www . geesforgeks . org/date-gettime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-gettime-method-in-java-with-examples/)

**Java Date 类**的 **getTime()** 方法返回自 1970 年 1 月 1 日 00:00:00 GTM 以来的毫秒数，用 Date 对象表示。

**语法:**

```
public long getTime()

```

**参数:**函数不接受任何参数。

**返回值:**返回 1970 年 1 月 1 日 00:00:00 GTM 以来的毫秒数。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

```
// Java code to demonstrate
// getTime() function of Date class

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

        System.out.println("Date: " + dateOne);

        System.out.println(dateOne.getTime());
    }
}
```

**Output:**

```
Date: Thu Dec 05 09:29:39 UTC 1996
849778179420

```

```
// Java code to demonstrate
// getTime() function of Date class

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
        c1.set(Calendar.YEAR, 2000);

        // creating a date object with specified time.
        Date dateOne = c1.getTime();

        System.out.println("Date: " + dateOne);

        System.out.println(dateOne.getTime());
    }
}
```

**Output:**

```
Date: Tue Dec 05 09:29:40 UTC 2000
976008580370

```