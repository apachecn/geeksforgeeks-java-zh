# Java 中的 MonthDay adjustInto()方法，带示例

> 原文:[https://www . geesforgeks . org/monthday-adjustin to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-adjustinto-method-in-java-with-examples/)

**调整()**月日**类的**方法，用于调整传递的时态对象，使其具有应用该方法的月日。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public Temporal adjustInto(Temporal temporal)

```

**参数:**该方法接受**时间**作为参数，该参数是要调整的目标时间对象。它不应为空。

**返回值:**此方法返回调整后的对象。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**-如果无法进行调整。

以下程序说明了 adjustInto()方法:
**程序 1:**

```java
// Java program to demonstrate
// MonthDay.adjustInto() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay mday = MonthDay.of(10, 31);

        // print instance
        System.out.println("MonthDay :"
                           + mday);

        // create a temporal object
        LocalDate date
 = LocalDate.parse("2007-12-03");

        // print instance
        System.out.println("LocalDate :"
                           + date);

        // apply adjustInto method of Year class
        LocalDate updatedlocal
 = (LocalDate)mday.adjustInto(date);

        // print instance
        System.out.println("LocalDate after"
                           + " applying adjustInto method: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
MonthDay :--10-31
LocalDate :2007-12-03
LocalDate after applying adjustInto method: 2007-10-31

```

**程序 2:**

```java
// Java program to demonstrate
// MonthDay.adjustInto() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay mday = MonthDay.of(12, 22);

        // print instance
        System.out.println("MonthDay :"
                           + mday);

        // create a temporal object
        LocalDate date
 = LocalDate.parse("2017-12-03");

        // print instance
        System.out.println("LocalDate :"
                           + date);

        // apply adjustInto method of Year class
        LocalDate updatedlocal 
= (LocalDate)mday.adjustInto(date);

        // print instance
        System.out.println("LocalDate after"
                           + " applying adjustInto method: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
MonthDay :--12-22
LocalDate :2017-12-03
LocalDate after applying adjustInto method: 2017-12-22

```

**参考文献:**T2