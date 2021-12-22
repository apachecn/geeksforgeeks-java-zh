# Java 中的 Calendar isLenient()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-islenient-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-islenient-method-in-java-with-examples/)

Calendar 类中的 **isLenient()** 方法是用来了解和理解这个 Calendar 的日期和时间解释是否算宽大。
**语法:**

```java
public boolean isLenient()
```

**参数:**该方法不取任何参数。
**返回值:**如果此日历的解释宽松，则该方法返回**真**否则返回**假**。
下面的程序说明了日历类的 isLenient()方法的工作:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// isLenient() method

import java.util.*;
public class CalendarDemo {
    public static void main(String args[])
    {

        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the calendar
        System.out.println("Current Calendar: "
                           + calndr.getTime());

        // Checking the leniency
        boolean leniency = calndr.isLenient();

        // Displaying the leniency
        System.out.println("Calendar is"
                           + " lenient: "
                           + leniency);
    }
}
```

**Output**

```java
Current Calendar: Tue Nov 30 10:25:50 UTC 2021
Calendar is lenient: true
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// isLenient() method

import java.util.*;
public class CalendarDemo {
    public static void main(String args[])
    {

        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the calendar
        System.out.println("Current Calendar: "
                           + calndr.getTime());

        // Checking the leniency
        boolean leniency = calndr.isLenient();
        calndr.setLenient(false);
        leniency = calndr.isLenient();

        // Displaying the leniency
        System.out.println("Calendar is"
                           + " lenient: "
                           + leniency);
    }
}
```

**Output**

```java
Current Calendar: Tue Nov 30 10:26:18 UTC 2021
Calendar is lenient: false
```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # isLenient–](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#isLenient--)