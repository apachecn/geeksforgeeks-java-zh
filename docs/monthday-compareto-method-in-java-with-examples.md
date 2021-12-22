# Java 中的 MonthDay compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/month day-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-compareto-method-in-java-with-examples/)

Java 中**月日类**的 **compareTo()** 方法将这个月日与另一个月日进行比较。

**语法:**

```java
public int compareTo(MonthDay other)
```

**参数:**该方法接受一个参数**其他**，该参数指定要比较的其他月日，不为空。

**返回:**功能返回**比较器值**。它可以是负的，如果它是小的，或者是正的，如果它是大的。

**异常**:如果另一个为空，函数抛出**空指针异常**。

以下程序说明了 **MonthDay.compareTo()** 方法:

**程序 1:**

```java
// Program to illustrate the compareTo() method

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
        System.out.println(dt1.compareTo(dt2));
    }
}
```

**输出:**

```java
0

```

**程序二:**

```java
// Program to illustrate the compareTo() method

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
        System.out.println(dt1.compareTo(dt2));
    }
}
```

**输出:**

```java
-2

```

**程序 3:**

```java
// Program to illustrate the compareTo() method

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
        MonthDay tm2 = MonthDay.parse("--09-06");

        // Uses the function
        LocalDate dt2 = tm2.atYear(2018);

        // Prints the date
        System.out.println(dt1.compareTo(dt2));
    }
}
```

**输出:**

```java
1

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/monthday . html # compare to-Java . time . monthday-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#compareTo-java.time.MonthDay-)