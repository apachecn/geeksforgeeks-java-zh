# Java 中的 MonthDay isAfter()方法，带示例

> 原文:[https://www . geesforgeks . org/month day-is after-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-isafter-method-in-java-with-examples/)

**isAfter()** 方法的**月日**类用来检查这个月日是否在作为参数传递的月日之后。此方法返回一个显示相同内容的布尔值。

**语法:**

```java
public boolean isAfter(MonthDay other)

```

**参数:**此方法接受一个参数**另一个参数**，即要比较的另一个月日。

**返回值:**如果这个月日在指定的月日之后，这个方法返回真，否则返回假。

下面的程序说明了 isAfter()方法:
**程序 1:**

```java
// Java program to demonstrate
// MonthDay.isAfter() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // create other MonthDay object
        MonthDay othermonth = MonthDay.parse("--11-12");

        // apply isAfter() method
        boolean value = month.isAfter(othermonth);

        // print instance
        System.out.println("monthday:"
                           + month + " is after monthday:"
                           + othermonth + " = "
                           + value);
    }
}
```

**Output:**

```java
monthday:--10-12 is after monthday:--11-12 = false

```

**程序 2:**

```java
// Java program to demonstrate
// MonthDay.isAfter() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // create other MonthDay object
        MonthDay othermonth = MonthDay.parse("--09-12");

        // apply isAfter() method
        boolean value = month.isAfter(othermonth);

        // print instance
        System.out.println("monthday:"
                           + month + " is after monthday:"
                           + othermonth + " = "
                           + value);
    }
}
```

**Output:**

```java
monthday:--10-12 is after monthday:--09-12 = true

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # isaafter(Java . time . monthday)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#isAfter(java.time.MonthDay))