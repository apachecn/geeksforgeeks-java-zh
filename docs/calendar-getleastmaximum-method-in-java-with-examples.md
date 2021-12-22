# Java 中 Calendar getLeastMaximum()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-getlestmaximum-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-getleastmaximum-method-in-java-with-examples/)

calendar 类中的**getlestmaximum(int*calndr _ field*)**方法用于返回此 Calendar 实例的给定日历字段(int calndr_field)的最小最大值。

**语法:**

```java
public abstract int getLeastMaximum(int *calndr_field*)
```

**参数:**该方法取一个参数 *calndr_field* ，指的是要操作的日历字段。

**返回值:**该方法返回该日历字段的最低最大值。

下面的程序说明了日历类的 getLeastMaximum()方法的工作:
**例 1:**

```java
// Java code to illustrate
// getLeastMaximum() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Getting the required months
        System.out.println("Required Months: "
                           + calndr.get(Calendar.MONTH));

        // Getting the lowest maximum month
        int low_max = calndr.getLeastMaximum(Calendar.MONTH);

        // Displaying the results
        System.out.println("The Lowest"
                           + " Maximum months: " + low_max);
    }
}
```

**Output:**

```java
Required Months: 1
The Lowest Maximum months: 11

```

**例 2:**

```java
// Java code to illustrate
// getLeastMaximum() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating a calendar
        Calendar calndr = new GregorianCalendar(2018, 6, 10);

        // Getting the required months
        System.out.println("Required Months: "
                           + calndr.get(Calendar.MONTH));

        // Getting the lowest maximum month
        int low_max = calndr.getLeastMaximum(Calendar.MONTH);

        // Displaying the results
        System.out.println("The Lowest"
                           + " Maximum months: " + low_max);
    }
}
```

**Output:**

```java
Required Months: 6
The Lowest Maximum months: 11

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # getlestmaximum-int-](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#getLeastMaximum-int-)