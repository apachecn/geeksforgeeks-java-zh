# Java 中的 Calendar toString()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-tostring-method-in-java-with-examples/)

[日历类](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/)中的 **toString()** 方法用于获取日历对象的字符串表示。Calendar 类中的这个方法只是用于调试过程，不能作为操作使用。

**语法:**

```java
public String toString()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回日历对象的字符串表示形式。它可以返回一个空对象，但不能为 null。

下面的程序说明了日历类的 toString()方法的工作原理:

**例 1:**

```java
// Java Code to illustrate toString() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr1
            = Calendar.getInstance();

        // Returning the string representation
        System.out.println("The string form: "
                           + calndr1.getTime()
                                 .toString());
    }
}
```

**输出:**

```java
The string form: Wed Feb 13 09:46:36 UTC 2019

```

**例 2:**

```java
// Java Code to illustrate toString() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr1
            = new GregorianCalendar(2018, 12, 2);

        // Returning the string representation
        System.out.println("The string form: "
                           + calndr1.getTime()
                                 .toString());
    }
}
```

**输出:**

```java
The string form: Wed Jan 02 00:00:00 UTC 2019

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # toString()](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#toString())