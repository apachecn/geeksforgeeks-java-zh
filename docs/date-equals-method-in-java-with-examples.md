# Java 中的 Date 等于()方法，示例

> 原文:[https://www . geesforgeks . org/date-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-equals-method-in-java-with-examples/)

**Java 日期类**的 **equals()** 方法根据毫秒差检查两个日期是否相等。

**语法:**

```
public boolean equals(Object obj)

```

**参数:**该函数接受单个参数**对象**，该参数指定要比较的对象。

**返回值:**该函数给出下面指定的 2 个返回值:

*   如果对象相等，则为 true。
*   如果对象不相等，则为 false。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

```
// Java code to demonstrate
// equals() function of Date class

import java.util.Date;
import java.util.Calendar;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a Calendar object
        Calendar c = Calendar.getInstance();

        // set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c.set(Calendar.MONTH, 11);

        // set Date
        c.set(Calendar.DATE, 05);

        // set Year
        c.set(Calendar.YEAR, 1996);

        // creating a date object with specified time.
        Date dateOne = c.getTime();

        System.out.println("Date 1: " + dateOne);

        // creating a date of object
        // storing the current date
        Date currentDate = new Date();

        System.out.println("Date 2: " + currentDate);

        System.out.println("Are both dates equal: "
                           + currentDate.equals(dateOne));
    }
}
```

**Output:**

```
Date 1: Thu Dec 05 08:19:56 UTC 1996
Date 2: Wed Jan 02 08:19:56 UTC 2019
Are both dates equal: false

```

```
// Java code to demonstrate
// equals() function of Date class

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

        System.out.println("Date 1: " + dateOne);

        // creating a Calendar object
        Calendar c2 = Calendar.getInstance();

        // set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c2.set(Calendar.MONTH, 11);

        // set Date
        c2.set(Calendar.DATE, 05);

        // set Year
        c2.set(Calendar.YEAR, 1995);

        // creating a date object with specified time.
        Date dateTwo = c2.getTime();

        System.out.println("Date 1: " + dateTwo);

        System.out.println("Are both dates equal: "
                           + dateTwo.equals(dateOne));
    }
}
```

**Output:**

```
Date 1: Thu Dec 05 08:20:05 UTC 1996
Date 1: Tue Dec 05 08:20:05 UTC 1995
Are both dates equal: false

```