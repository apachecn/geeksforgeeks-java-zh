# 月日发布 Java 中的支持()方法，示例

> 原文:[https://www . geesforgeks . org/month day-issupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-issupported-method-in-java-with-examples/)

**用于检查指定字段是否被月日类支持的**月日**类的 isSupported()** 方法意味着使用该方法我们可以检查是否可以为指定字段查询该月日。

计时场支持的字段有:

*   **年月日**
*   **年**

所有其他时间域实例都将返回 false。

**语法:**

```
public boolean isSupported(TemporalField field)
```

**参数:**该方法接受一个参数**字段**，该字段是要检查的字段。
**返回值:**如果该月日支持该字段，则该方法返回布尔值 true，否则返回 false。

下面的程序说明了 isSupported()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// MonthDay.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // apply isSupported() method
        boolean value
            = month.isSupported(
                ChronoField.MONTH_OF_YEAR);

        // print result
        System.out.println("MONTH_OF_YEAR Field is supported: "
                           + value);
    }
}
```

**Output:** 

```
MONTH_OF_YEAR Field is supported: true
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// MonthDay.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // apply isSupported() method
        boolean value
            = month.isSupported(
                ChronoField.MILLI_OF_SECOND);

        // print result
        System.out.println("MilliSecond Field is supported: "
                           + value);
    }
}
```

**Output**

```
MilliSecond Field is supported: false
```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # isSupported(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#isSupported(java.time.temporal.TemporalField))