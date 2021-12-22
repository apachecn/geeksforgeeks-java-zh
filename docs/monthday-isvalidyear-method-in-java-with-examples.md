# MonthDay 是 Java 中的有效年份()方法，带示例

> 原文:[https://www . geesforgeks . org/month day-is valid year-in-Java-method-with-examples/](https://www.geeksforgeeks.org/monthday-isvalidyear-method-in-java-with-examples/)

**是**月日**类的**方法，用于检查指定的年份在本月日是否有效。这只能为 2 月 29 日返回 false。

**语法:**

```
public boolean isValidYear?(int year)

```

**参数:**该方法接受一个参数**年份**，即需要验证的年份。

**返回值:**如果年对此月日有效，则该方法返回布尔值 true。

下面的程序说明了 isValidYear()方法:
**程序 1:**

```
// Java program to demonstrate
// MonthDay.isValidYear() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // apply isValidYear() method
        boolean value = month.isValidYear(2012);

        // print result
        System.out.println("Year 2012 is valid for monthday: "
                           + month + " = " + value);
    }
}
```

**Output:**

```
Year 2012 is valid for monthday: --10-12 = true

```

**程序 2:**

```
// Java program to demonstrate
// MonthDay.isValidYear() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--02-29");

        // apply isValidYear() method
        boolean value = month.isValidYear(2017);

        // print result
        System.out.println("Year 2017 is valid for monthday: "
                           + month + " = " + value);
    }
}
```

**Output:**

```
Year 2017 is valid for monthday: --02-29 = false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # isValidYear(int)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#isValidYear(int))