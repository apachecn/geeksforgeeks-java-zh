# Java 中的 Date toString()方法，带示例

> 原文:[https://www . geesforgeks . org/date-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-tostring-method-in-java-with-examples/)

**Java Date 类**的 **toString()** 方法将该日期对象转换为“dow mon dd hh:mm:ss zzz yyy”形式的字符串。此方法重写类对象中的 toString。
**语法:**

```
public String toString()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回该日期的字符串表示形式。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

```
// Java code to demonstrate
// toString() function of Date class

import java.util.Date;
import java.util.Calendar;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 11);

        // set Date
        c1.set(Calendar.DATE, 05);

        // set Year
        c1.set(Calendar.YEAR, 1996);

        // creating a date object with specified time.
        Date dateOne = c1.getTime();

        System.out.println(dateOne.toString());
    }
}
```

**Output:**

```
Thu Dec 05 08:21:00 UTC 1996

```

```
// Java code to demonstrate
// toString() function of Date class

import java.util.Date;
import java.util.Calendar;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 11);

        // set Date
        c1.set(Calendar.DATE, 15);

        // set Year
        c1.set(Calendar.YEAR, 1999);

        // creating a date object with specified time.
        Date dateOne = c1.getTime();

        System.out.println(dateOne.toString());
    }
}
```

**Output:**

```
Wed Dec 15 08:21:02 UTC 1999

```