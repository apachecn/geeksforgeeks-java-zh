# Java 中的 MonthDay isBefore()方法，带示例

> 原文:[https://www . geesforgeks . org/month day-is before-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-isbefore-method-in-java-with-examples/)

**是**月日**类的方法，用于检查该月日是否在作为参数传递的月日之前。此方法返回一个显示相同内容的布尔值。**

**语法:**

```
public boolean isBefore(MonthDay other)

```

**参数:**此方法接受一个参数**另一个参数**，即要比较的另一个月日。

**返回值:**如果这个月日在指定的月日之前，这个方法返回真，否则返回假。

以下程序说明了 isBefore()方法:
**程序 1:**

```
// Java program to demonstrate
// MonthDay.isBefore() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // create other MonthDay object
        MonthDay othermonth = MonthDay.parse("--11-12");

        // apply isBefore() method
        boolean value = month.isBefore(othermonth);

        // print instance
        System.out.println("monthday:"
                           + month + " is before monthday:"
                           + othermonth + " = "
                           + value);
    }
}
```

**Output:**

```
monthday:--10-12 is before monthday:--11-12 = true

```

**程序 2:**

```
// Java program to demonstrate
// MonthDay.isBefore() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // create other MonthDay object
        MonthDay othermonth = MonthDay.parse("--09-12");

        // apply isBefore() method
        boolean value = month.isBefore(othermonth);

        // print instance
        System.out.println("monthday:"
                           + month + " is before monthday:"
                           + othermonth + " = "
                           + value);
    }
}
```

**Output:**

```
monthday:--10-12 is before monthday:--09-12 = false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # is before(Java . time . monthday)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#isBefore(java.time.MonthDay))