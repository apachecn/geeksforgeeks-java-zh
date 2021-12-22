# Java 中的 Instant plus()方法，示例

> 原文:[https://www . geesforgeks . org/instant-plus-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-plus-method-in-java-with-examples/)

在 Instant 类中，根据传递给它的参数，有两种类型的 plus()方法。

### 加(long amountToAdd，temporalunit unit)

**plus()** 一个**瞬发**类的方法，用来返回这个瞬发的副本，并添加指定数量的单位。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public Instant plus(long amountToAdd,
                    TemporalUnit unit)

```

**参数:**该方法接受两个参数 **amountToAdd** 可以为负数，也可以接受 **unit** 为要相加的金额单位，不为空。

**返回值:**此方法返回**瞬间**基于此瞬间加上指定的金额。

下面的程序说明了加号()方法:
**程序 1:**

```
// Java program to demonstrate
// Instant.plus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create an Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // add 30 DAYS to Instant
        Instant value
            = instant.plus(30, ChronoUnit.DAYS);

        // print result
        System.out.println("Instant after adding 30 DAYS: "
                           + value);
    }
}
```

**Output:**

```
Instant after adding 30 DAYS: 2019-01-29T19:34:50.630Z

```

### amounttoadd 临时挂载)

**plus()** 方法的一个**瞬间**类用来返回这个瞬间的一个副本，指定的数量加到日期时间。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```
public Instant plus(TemporalAmount amountToAdd)

```

**参数:**此方法只接受一个参数**金额加**即要加的金额，不应该为空。

**返回值:**该方法返回**时刻**基于该时刻进行加法运算，不为空

下面的程序说明了加号()方法:
**程序 1:**

```
// Java program to demonstrate
// Instant.plus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant inst
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // add 20 Days to Instant
        Instant value
            = inst.plus(Period.ofDays(10));

        // print result
        System.out.println("Instant after adding Days: "
                           + value);
    }
}
```

**Output:**

```
Instant after adding Days: 2019-01-09T19:34:50.630Z

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # plus(java.time .时态. tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#plus(java.time.temporal.TemporalAmount))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # plus(long，Java . time .时态. tempalalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#plus(long, java.time.temporal.TemporalUnit))