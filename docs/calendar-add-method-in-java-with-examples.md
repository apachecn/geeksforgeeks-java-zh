# Java 中的日历添加()方法，示例

> 原文:[https://www . geesforgeks . org/calendar-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-add-method-in-java-with-examples/)

存在于内部的[日历类](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/)的 ***add()方法*** 用于根据日历的规则从给定的日历字段(int 字段)中添加或减去特定的时间量(int amt)。

**语法:**

```java
public abstract void add(int *field*, int *amt*)
```

**参数:**该方法取两个参数:

*   要在其上执行操作的日历字段。(整数类型)
*   需要减去的时间量。(整数类型)

**返回值:**该方法不返回值。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate add() Method
// of Calendar class

// Importing required classes
import java.util.Calendar;

// Main class
public class CalendarClassDemo {

    // Main driver method
    public static void main(String args[])
    {
        // Creating a Calendar class object
        Calendar calndr = Calendar.getInstance();

        // Displaying the current date
        // using getTime() method
        System.out.println("Current Date: "
                           + calndr.getTime());

        // Adding 50 days to the
        // Current Calendar
        // using add() method
        calndr.add(Calendar.DATE, 50);

        // Displaying the date now using getTime() method
        System.out.println("After 50 days: "
                           + calndr.getTime());

        // Subtracting 6 months from
        // the Current calendar
        calndr.add(Calendar.MONTH, -6);

        // Displaying the date now using getTime() method
        System.out.println("6 months ago it was: "
                           + calndr.getTime());

        // Subtracting 2 year from
        // the Current calendar
        calndr.add(Calendar.YEAR, -2);

        // Displaying the date now using getTime() method
        System.out.println("2 years ago it was: "
                           + calndr.getTime());
    }
}
```

**Output:** 

```java
Current Date: Tue Feb 12 10:54:21 UTC 2019
After 50 days: Wed Apr 03 10:54:21 UTC 2019
6 months ago it was: Wed Oct 03 10:54:21 UTC 2018
2 years ago it was: Mon Oct 03 10:54:21 UTC 2016
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate add() Method
// of Calendar class

// Importing required classes
import java.util.Calendar;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the current date
        // using getTime() method
        System.out.println("Current Date: "
                           + calndr.getTime());

        // Adding 30 days to the current calendar
        // using add() method
        calndr.add(Calendar.DATE, 30);

        // Printing the corresponding date
        System.out.println("After 30 days: "
                           + calndr.getTime());

        // Subtracting 3 months from the current calendar
        calndr.add(Calendar.MONTH, -3);

        // Printing the corresponding date
        System.out.println("3 months ago it was: "
                           + calndr.getTime());

        // Subtracting 10 years from
        // the Current calendar
        calndr.add(Calendar.YEAR, -10);

        // Printing the corresponding date
        System.out.println("10 years ago it was: "
                           + calndr.getTime());
    }
}
```

**Output:** 

```java
Current Date: Tue Feb 12 10:54:24 UTC 2019
After 30 days: Thu Mar 14 10:54:24 UTC 2019
3 months ago it was: Fri Dec 14 10:54:24 UTC 2018
10 years ago it was: Sun Dec 14 10:54:24 UTC 2008
```