# Java 中的日历克隆()方法，示例

> 原文:[https://www . geesforgeks . org/calendar-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-clone-method-in-java-with-examples/)

Calendar 类中的 **clear()** 方法用于克隆日历对象。它基本上创建了这个对象的一个浅拷贝。

**语法:**

```java
public Object clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法不返回值。

下面的程序说明了 Calendar 类的 clone()方法的工作:
**例 1:**

```java
// Java Code to illustrate clone() Method

import java.util.Calendar;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr1 = Calendar.getInstance();

        // Displaying current calendar
        System.out.println("Original calendar: "
                           + calndr1.getTime());

        // Cloning the original
        Calendar calndr2 = (Calendar)calndr1.clone();

        // Displaying the Copy
        System.out.println("Cloned calendar: "
                           + calndr2.getTime());
    }
}
```

**Output:**

```java
Original calendar: Tue Feb 12 11:41:36 UTC 2019
Cloned calendar: Tue Feb 12 11:41:36 UTC 2019

```

**例 2:**

```java
// Java Code to illustrate clone() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr1
            = new GregorianCalendar(2018, 12, 2);

        // Displaying current calendar
        System.out.println("Original calendar: "
                           + calndr1.getTime());

        // Cloning the original
        Calendar calndr2 = (Calendar)calndr1.clone();

        // Displaying the Copy
        System.out.println("Cloned calendar: "
                           + calndr2.getTime());
    }
}
```

**Output:**

```java
Original calendar: Wed Jan 02 00:00:00 UTC 2019
Cloned calendar: Wed Jan 02 00:00:00 UTC 2019

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # clone()](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#clone())