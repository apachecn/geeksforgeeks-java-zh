# Java 中的 LocalDateTime plus()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-plus-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-plus-method-in-java-with-examples/)

在 LocalDateTime 类中，根据传递给它的参数，有两种类型的 plus()方法。

### 加(long amountToAdd，temporalunit unit)

**plus()** 一个 **LocalDateTime** 类的方法，用于返回该 LocalDateTime 的副本，并添加指定数量的单位。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public LocalDateTime plus(long amountToAdd,
                          TemporalUnit unit)

```

**参数:**该方法接受两个参数 **amountToAdd** 可以为负数，也可以接受 **unit** 为要相加的金额单位，不为空。

**返回值:**该方法基于添加了指定金额的本地日期时间返回**本地日期时间**。

下面的程序说明了加号()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.plus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation
        // of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + ldt.toString());

        // add 90 DAYS to LocalDateTime
        LocalDateTime value
            = ldt.plus(90, ChronoUnit.DAYS);

        // print result
        System.out.println("LocalDateTime after"
                           + " adding 30 DAYS: "
                           + value);
    }
}
```

**Output:**

```java
Original LocalDateTime: 2019-12-31T19:15:30
LocalDateTime after adding 30 DAYS: 2020-03-30T19:15:30

```

### amounttoadd 临时挂载)

**plus()** 一个 **LocalDateTime** 类的方法，用于返回该 LocalDateTime 的一个副本，其中指定的数量被添加到日期时间中。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
public LocalDateTime plus(TemporalAmount amountToAdd)

```

**参数:**此方法只接受一个参数**金额加**即要加的金额，不应该为空。

**返回值:**此方法基于此 LocalDateTime 返回 **LocalDateTime** ，并进行加法运算，不为空

下面的程序说明了加号()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.plus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation
        // of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + ldt.toString());

        // add 20 Days to LocalDateTime
        LocalDateTime value
            = ldt.plus(Period.ofDays(10));

        // print result
        System.out.println("LocalDateTime after"
                           + " adding Days: "
                           + value);
    }
}
```

**Output:**

```java
Original LocalDateTime: 2019-12-31T19:15:30
LocalDateTime after adding Days: 2020-01-10T19:15:30

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plus(Java . time . temporalamont)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plus(java.time.temporal.TemporalAmount))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plus(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plus(long, java.time.temporal.TemporalUnit))