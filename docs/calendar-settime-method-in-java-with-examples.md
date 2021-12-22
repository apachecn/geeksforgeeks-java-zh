# Java 中的日历设置时间()方法，示例

> 原文:[https://www . geesforgeks . org/calendar-settime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-settime-method-in-java-with-examples/)

Calendar 类中的**设置时间(日期 *dt* )** 方法用于设置由该 Calendar 的时间值表示的 Calendar 时间，给定或过去的日期作为参数。

**语法:**

```java
public final void setTime(Date *dt*))
```

**参数:**该方法取日期类型的一个参数 **dt** ，指的是要设置的给定日期。

**返回值:**该方法不返回值。

下面的程序说明了日历类的 setTime()方法的工作:
**例 1:**

```java
// Java code to illustrate
// setTime() method

import java.util.*;
public class Calendar_Demo
    extends GregorianCalendar {
    public static void main(String[] args)
    {
        // Creating calendar objects
        Calendar calndr1
            = (Calendar)Calendar.getInstance();
        Calendar calndr2
            = (Calendar)Calendar.getInstance();

        // Displaying the current date
        System.out.println("The Current"
                           + " System Date: "
                           + calndr1.getTime());

        // Setting to a different date
        calndr1.set(Calendar.MONTH, 5);
        calndr1.set(Calendar.YEAR, 2006);
        calndr1.set(Calendar.DAY_OF_WEEK, 15);
        Date dt = calndr1.getTime();

        // Setting the timevalue
        calndr2.setTime(dt);

        // Displaying the new date
        System.out.println("The modified"
                           + " Date:"
                           + calndr2.getTime());
    }
}
```

**Output:**

```java
The Current System Date: Fri Feb 22 07:33:13 UTC 2019
The modified Date:Sun Jun 18 07:33:13 UTC 2006

```

**例 2:**

```java
// Java code to illustrate
// setTime() method

import java.util.*;

public class Calendar_Demo
    extends GregorianCalendar {

    public static void main(String[] args)
    {
        // Creating calendar objects
        Calendar calndr1
            = (Calendar)Calendar.getInstance();
        Calendar calndr2
            = (Calendar)Calendar.getInstance();

        // Displaying the current date
        System.out.println("The Current"
                           + " System Date: "
                           + calndr1.getTime());

        // Setting to a different date
        calndr1.set(Calendar.MONTH, 10);
        calndr1.set(Calendar.YEAR, 1995);
        calndr1.set(Calendar.DAY_OF_WEEK, 20);
        Date dt = calndr1.getTime();

        // Setting the timevalue
        calndr2.setTime(dt);

        // Displaying the new date
        System.out.println("The modified"
                           + " Date: "
                           + calndr2.getTime());
    }
}
```

**Output:**

```java
The Current System Date: Fri Feb 22 07:33:20 UTC 2019
The modified Date: Fri Nov 24 07:33:20 UTC 1995

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # setTime(Java . util . date)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#setTime(java.util.Date))