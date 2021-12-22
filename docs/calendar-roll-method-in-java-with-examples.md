# Java 中的日历滚动()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-roll-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-roll-method-in-java-with-examples/)

Calendar 类中的 **roll(int *calndr_field* 、boolean *up_down* )** 方法用于通过将传递的字段上移或下移一个时间单位来对传递的日历字段进行操作。这包括在不改变较大场的情况下增加或减少时间场。

**语法:**

```java
public abstract void roll(int *calndr_field*, boolean *up_down*)
```

**参数:**该方法取两个参数:

*   **日历字段**:这是日历类型，是指要操作的日历的字段。
*   **up_down** :这是布尔类型，用于指示是向上还是向下移动 calndr_field，还是增加或减少。true 表示加上时间单位，false 表示减去时间单位。

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
        // false indicates subtraction
        calndr.roll(Calendar.YEAR, false);

        // Displaying the result after operation
        System.out.println("The New Year is: "
                           + calndr.get(
                                 Calendar.YEAR));

        // Incrementing the year
        // true indicates addition
        calndr.roll(Calendar.YEAR, true);

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
The New Year is: 2018
The new year is: 2019

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
        // true indicates addition
        calndr.roll(Calendar.MONTH, true);

        // Displaying the result after operation
        System.out.println("The New Month is: "
                           + calndr.get(
                                 Calendar.MONTH));

        // Decrementing the month
        // false indicates subtraction
        calndr.roll(Calendar.MONTH, false);

        // Displaying the result after operation
        System.out.println("The new month is: "
                           + calndr.get(
                                 Calendar.MONTH));
    }
}
```

**Output:**

```java
The Current Month is: 1
The New Month is: 2
The new month is: 1

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # roll-int-boolean-](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#roll-int-boolean-)