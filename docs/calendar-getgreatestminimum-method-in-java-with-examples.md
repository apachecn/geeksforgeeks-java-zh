# Java 中 Calendar getGreatestMinimum()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-getgreatest minimum-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-getgreatestminimum-method-in-java-with-examples/)

calendar 类中的**getgreateestminimum(int*calndr _ field*)**方法用于返回此 Calendar 实例的给定日历字段(int calndr_field)的最高最小值。

**语法:**

```java
public abstract int getGreatestMinimum(int *calndr_field*)
```

**参数:**该方法取一个参数 *calndr_field* ，指的是要操作的日历字段。

**返回值:**该方法返回该日历字段的最低最大值。

下面的程序说明了日历类的 getGreatestMinimum()方法的工作:
**例 1:**

```java
// Java code to illustrate
// getGreatestMinimum() method

import java.util.*;
public class Java_Calendar_Demo {
    public static void main(String[] args)
    {
        // Creating a calendar
        Calendar calndr = new GregorianCalendar(2018, 6, 10);

        // Calculating the highest min value
        int rslt = calndr.getGreatestMinimum(Calendar.YEAR);

        // Displaying the highest min value
        System.out.println("The minimum year is: " + rslt);
    }
}
```

**Output:**

```java
The minimum year is: 1

```

**例 2:**

```java
// Java code to illustrate
// getGreatestMinimum() method

import java.util.*;
public class Java_Calendar_Demo {
    public static void main(String[] args)
    {
        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Calculating the highest min value
        int rslt = calndr.getGreatestMinimum(Calendar.MONTH);

        // Displaying the highest min value
        System.out.println("The minimum month is: " + rslt);
    }
}
```

**Output:**

```java
The minimum month is: 0

```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # getgreateestminimum(int)