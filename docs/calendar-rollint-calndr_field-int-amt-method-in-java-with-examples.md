# Java 中日历滚动(int calndr_field，int amt)方法，示例

> 原文:[https://www . geesforgeks . org/calendar-roll int-calndr _ field-int-AMT-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-rollint-calndr_field-int-amt-method-in-java-with-examples/)

[日历类](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/)中的 **roll(int *calndr_field* 、int *amt* )** 方法用于对通过的日历字段进行操作，将通过的金额添加到特定的日历字段中，而不改变大的字段值。
**注:**必须加正数，必须减负数。

**语法:**

> 公共无效卷(int *calndr_field* ，int *amt*

**参数:**该方法取两个参数:

1.  *日历字段:*这是日历类型，指要操作的日历字段。
2.  *amt:* 这是整数类型，根据数值的符号进行加减。

**返回值:**该方法不返回值。

以下程序说明了日历类 roll()方法的工作:
**示例 1:**

```java
// Java code to illustrate
// isSet() method

import java.util.*;
public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Displaying the year
        System.out.println("The Current Year"
                           + " is: "
                           + calndr.get(
                                 Calendar.YEAR));

        // Decrementing the year
        // by 5
        calndr.roll(Calendar.YEAR, -5);

        // Displaying the result after the operation
        System.out.println("The New Year is: "
                           + calndr.get(
                                 Calendar.YEAR));

        // Incrementing the year
        // by 2
        calndr.roll(Calendar.YEAR, 2);

        // Displaying the result after operation
        System.out.println("The new year is: "
                           + calndr.get(
                                 Calendar.YEAR));
    }
}
```

**Output:**

```java
The Current Year is: 2019
The New Year is: 2014
The new year is: 2016

```

**例 2:**

```java
// Java code to illustrate
// isSet() method

import java.util.*;
public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Displaying the month
        System.out.println("The Current Month"
                           + " is: "
                           + calndr.get(
                                 Calendar.MONTH));

        // Incrementing the month
        // by 3
        calndr.roll(Calendar.MONTH, 3);

        // Displaying the result after operation
        System.out.println("The New Month is: "
                           + calndr.get(
                                 Calendar.MONTH));

        // Decrementing the month
        // by 1
        calndr.roll(Calendar.MONTH, -1);

        // Displaying the result after operation
        System.out.println("The new month is: "
                           + calndr.get(
                                 Calendar.MONTH));
    }
}
```

**Output:**

```java
The Current Month is: 2
The New Month is: 5
The new month is: 4

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # roll(int，%20int)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#roll(int, %20int))