# Java 中的 Calendar getInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-getinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-getinstance-method-in-java-with-examples/)

Calendar 类中的 **getInstance()** 方法用于获取使用系统当前时区和地区的日历。

**语法:**

```
public static Calendar getInstance()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回日历。

下面的程序说明了日历类的 getInstance()方法的工作:
**示例:**

```
// Java code to illustrate
// getGreatestMinimum() method

import java.util.*;
public class Java_Calendar_Demo {
    public static void main(String args[])
    {
        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Display the date and time
        System.out.print("The system"
                         + " date and time is: " + calndr.getTime());
    }
}
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # getInstance()](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#getInstance())