# Java 中的月日解析(CharSequence)方法，示例

> 原文:[https://www . geesforgeks . org/month day-parser charsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-parsecharsequence-method-in-java-with-examples/)

Java 中 **MonthDay** 类的 **parse(CharSequence text)** 方法用于从文本字符串中获取 **MonthDay** 的实例。
**语法:**

```
public static MonthDay parse(
    CharSequence text)
```

**参数:**该方法接受**文本**作为参数进行解析。

**返回值:**该方法返回解析后的**月-日**。

**异常:**如果文本无法解析，该方法抛出**datetime arseeexception**。

下面的程序说明了 Java 中 MonthDay 的解析(CharSequence text)方法:

**程序 1:**

```
// Java program to demonstrate
// MonthDay.parse(CharSequence text) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply parse(CharSequence text) method
        // of MonthDay class
        MonthDay monthday = MonthDay.parse(
            "--05-09");

        // print both month and day
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
// MonthDay.parse(CharSequence text) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply parse(CharSequence text) method
        // of MonthDay class
        MonthDay monthday = MonthDay.parse(
            "--05-09");

        // print only month
        System.out.println("Month: "
                           + monthday.getMonth());
    }
}
```

**Output:**

```
Month: MAY

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # parse(Java . lang . charsequence)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#parse(java.lang.CharSequence))