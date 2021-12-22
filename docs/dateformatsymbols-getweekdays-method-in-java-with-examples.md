# Java 中的日期格式符号 getWeekdays()方法，带示例

> 原文:[https://www . geesforgeks . org/dateformatsymbols-get weekdays-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-getweekdays-method-in-java-with-examples/)

Java 中 **DateFormatSymbols 类**的 **getWeekdays()** 方法用于获取字符串格式的日历工作日名称。

**语法:**

```java
public String[] getWeekdays()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以字符串格式返回工作日的名称。

下面的程序说明了 getWeekdays()方法的使用。
**例 1:**

```java
// Java code to demonstrate getWeekdays()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {
        int i;

        // Initializing DateFormatSymbols
        String wkdays[]
            = new DateFormatSymbols().getWeekdays();

        for (i = 1; i < wkdays.length; i++) {

            // Displaying the weekdays
            System.out.println("Day " + i
                               + " = " + wkdays[i]);
        }
    }
}
```

**Output:**

```java
Day 1 = Sunday
Day 2 = Monday
Day 3 = Tuesday
Day 4 = Wednesday
Day 5 = Thursday
Day 6 = Friday
Day 7 = Saturday

```

**例 2:**

```java
// Java code to demonstrate getWeekdays()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {
        int i;

        // Initializing DateFormatSymbols
        String wkdays[]
            = new DateFormatSymbols().getWeekdays();

        for (i = 1; i < wkdays.length / 2; i++) {

            // Displaying the weekdays
            System.out.println("Day " + i
                               + " = " + wkdays[i]);
        }
    }
}
```

**Output:**

```java
Day 1 = Sunday
Day 2 = Monday
Day 3 = Tuesday

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/text/dateformatsymbols . html # getWeekdays–](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#getWeekdays--)