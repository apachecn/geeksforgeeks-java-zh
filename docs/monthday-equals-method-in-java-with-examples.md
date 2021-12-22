# Java 中的 MonthDay 等于()方法，示例

> 原文:[https://www . geesforgeks . org/monthday-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-equals-method-in-java-with-examples/)

Java 中**月日类**的**等于()**方法检查这个月日是否等于另一个月日。

**语法:**

```java
public boolean equals(Object obj)
```

**参数:**这个方法接受一个参数 **obj** ，这个参数指定这个月日是否等于另一个月日。

**返回:**如果这个时间等于另一个时间，函数返回真。

以下程序说明了**月日等于()**方法:

**程序 1:**

```java
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2018);

        // Parses the date
        MonthDay tm2 = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt2 = tm2.atYear(2018);

        // Prints the date
        System.out.println(dt1.equals(dt2));
    }
}
```

**输出:**

```java
true

```

**程序二:**

```java
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--10-06");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2018);

        // Parses the date
        MonthDay tm2 = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt2 = tm2.atYear(2018);

        // Prints the date
        System.out.println(dt1.equals(dt2));
    }
}
```

**输出:**

```java
false

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/monthday . html # equals-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#equals-java.lang.Object-)