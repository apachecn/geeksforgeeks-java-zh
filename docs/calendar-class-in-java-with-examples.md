# Java 中的日历类，带示例

> 原文:[https://www . geesforgeks . org/calendar-class-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/)

Java 中的 Calendar 类是一个抽象类，它提供了在特定时刻和一组日历字段(如 MONTH、YEAR、HOUR 等)之间转换日期的方法。它继承了对象类，并实现了可比较、可序列化、可克隆的接口。

因为它是一个抽象类，所以我们不能使用构造函数来创建实例。相反，我们将不得不使用静态方法 Calendar.getInstance()来实例化和实现一个子类。

*   Calendar.getInstance (): Returns a Calendar instance with the default locale according to the current time in the default time zone.
*   Instance (Time Zone)
*   Example calendar (regional scope)
*   Instance (time zone, region range)

**Java 程序演示 getInstance()方法** :

```
// Date getTime(): It is used to return a
// Date object representing this
// Calendar's time value.

import java.util.*;
public class Calendar1 {
    public static void main(String args[])
    {
        Calendar c = Calendar.getInstance();
        System.out.println("The Current Date is:" + c.getTime());
    }
}
```

**输出:**

```
The Current Date is:Tue Aug 28 11:10:40 UTC 2018

```