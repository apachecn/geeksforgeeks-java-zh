# Java 中的 LocalTime plus()方法，示例

> 原文:[https://www . geesforgeks . org/local time-plus-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-plus-method-in-java-with-examples/)

在 LocalTime 类中，根据传递给它的参数，有两种类型的 plus()方法。

### 加(long amountToAdd，temporalunit unit)

**plus()** 一个 **LocalTime** 类的方法，用于返回该 LocalTime 的副本，并添加指定数量的单位。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。这个 LocalTime 对象是不可变的，不受这个方法调用的影响。

**语法:**

```java
public LocalTime plus(long amountToAdd,
                      TemporalUnit unit)

```

**参数:**该方法接受两个参数 **amountToAdd** 可以为负数，也可以接受 **unit** 为要相加的金额单位，不为空。

**返回值:**该方法基于该本地时间返回**本地时间**，并添加指定的金额。

下面的程序说明了加号()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalTime.plus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create an LocalTime object
        LocalTime lt
            = LocalTime.parse("19:34:50.63");

        // add 2 Hours to LocalTime
        LocalTime value
            = lt.plus(2, ChronoUnit.HOURS);

        // print result
        System.out.println("LocalTime after adding 2 Hours: "
                           + value);
    }
}
```

**Output:**

```java
LocalTime after adding 2 Hours: 21:34:50.630

```

### amounttoadd 临时挂载)

**plus()** 一个 **LocalTime** 类的方法，用于返回该 LocalTime 的一个副本，其中指定的数量被添加到日期时间中。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
public LocalTime plus(TemporalAmount amountToAdd)

```

**参数:**此方法只接受一个参数**金额加**即要加的金额，不应该为空。

**返回值:**此方法基于此本地时间返回**本地时间**，并进行加法运算，不为空

下面的程序说明了加号()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalTime.plus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime lt
            = LocalTime.parse("19:34:50.63");

        // add 55 Minutes to LocalTime
        LocalTime value
            = lt.plus(Duration.ofMinutes(55));

        // print result
        System.out.println("LocalTime after adding 55 Minutes: "
                           + value);
    }
}
```

**Output:**

```java
LocalTime after adding 55 Minutes: 20:29:50.630

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # plus(java.time .时态. tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#plus(java.time.temporal.TemporalAmount))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # plus(long，Java . time .时态. tempalalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#plus(long, java.time.temporal.TemporalUnit))