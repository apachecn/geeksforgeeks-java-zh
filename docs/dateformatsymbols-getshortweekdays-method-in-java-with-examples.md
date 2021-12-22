# Java 中的日期格式符号 getShortWeekdays()方法，带示例

> 原文:[https://www . geesforgeks . org/dateformatsymbols-getshortweekdays-Java 中的方法-示例/](https://www.geeksforgeeks.org/dateformatsymbols-getshortweekdays-method-in-java-with-examples/)

Java 中 **DateFormatSymbols 类**的 **getShortWeekdays()** 方法用于获取字符串格式的日历工作日的简称。例如，“太阳”代表周日，“周一”代表周一等等。

**语法:**

```
public String[] getShortWeekdays()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以字符串格式返回工作日的简称。

下面的程序说明了 getShortWeekdays()方法的使用。
**例 1:**

```
// Java code to demonstrate getShortWeekdays()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {
        int i;

        // Initializing DateFormatSymbols
        String shwkdays[]
            = new DateFormatSymbols().getShortWeekdays();

        for (i = 1; i < shwkdays.length; i++) {

            // Displaying the short names of weekdays
            System.out.println("Day " + i
                               + " = " + shwkdays[i]);
        }
    }
}
```

**Output:**

```
Day 1 = Sun
Day 2 = Mon
Day 3 = Tue
Day 4 = Wed
Day 5 = Thu
Day 6 = Fri
Day 7 = Sat

```

**例 2:**

```
// Java code to demonstrate getShortWeekdays()
import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {
        int i;

        // Initializing DateFormatSymbols
        String shwkdays[]
            = new DateFormatSymbols().getShortWeekdays();

        for (i = 1; i < shwkdays.length / 2; i++) {

            // Displaying the short names of weekdays
            System.out.println("Day " + i
                               + " = " + shwkdays[i]);
        }
    }
}
```

**Output:**

```
Day 1 = Sun
Day 2 = Mon
Day 3 = Tue

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/text/dateformatsymbols . html # getShortWeekdays–](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#getShortWeekdays--)