# Java 中的 MonthDay 解析(CharSequence，DateTimeFormatter)方法

> 原文:[https://www . geesforgeks . org/month day-parser charsequence-datetime formatter-method-in-Java/](https://www.geeksforgeeks.org/monthday-parsecharsequence-datetimeformatter-method-in-java/)

Java 中 **MonthDay** 类的**解析(CharSequence text，DateTimeFormatter】方法用于使用特定的格式化程序从文本字符串中获取 **MonthDay** 的实例。
**语法:****

```
public static MonthDay parse(
    CharSequence text, 
    DateTimeFormatter formatter)
```

**参数:**此方法接受

*   **文本**作为参数进行解析和
*   **格式化程序**作为参数使用。

**返回值:**该方法返回解析后的**月-日**。

**异常:**如果文本无法解析，该方法抛出**datetime arseeexception**。

下面的程序说明了 Java 中 MonthDay 的解析方法:

**程序 1:**

```
// Java program to demonstrate
// MonthDay.parse(CharSequence text,
// DateTimeFormatter formatter) method

import java.time.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply ofpattern() method
        // of DateTimeFormatter class
        DateTimeFormatter datetimeformatter
            = DateTimeFormatter.ofPattern("--MM-dd");

        // apply parse(CharSequence text,
        // DateTimeFormatter formatter) method
        // of MonthDay class
        MonthDay monthday = MonthDay.parse(
            "--05-09", datetimeformatter);

        // print monthday
        // in mm-dd format
        System.out.println("MonthDay: "
                           + monthday);
    }
}
```

**Output:**

```
MonthDay: --05-09

```

**程序 2:**

```
// Java program to demonstrate
// MonthDay.parse(CharSequence text,
// DateTimeFormatter formatter) method

import java.time.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply ofpattern() method
        // of DateTimeFormatter class
        DateTimeFormatter datetimeformatter
            = DateTimeFormatter.ofPattern("--dd-MM");

        // apply parse(CharSequence text,
        // DateTimeFormatter formatter) method
        // of MonthDay class
        MonthDay monthday = MonthDay.parse(
            "--05-09", datetimeformatter);

        // print monthday
        // in dd-mm format
        System.out.println("MonthDay: "
                           + monthday);
    }
}
```

**Output:**

```
MonthDay: --09-05

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # parse(Java . lang . charsequence，Java . time . format . datetime formatter)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#parse(java.lang.CharSequence, java.time.format.DateTimeFormatter))