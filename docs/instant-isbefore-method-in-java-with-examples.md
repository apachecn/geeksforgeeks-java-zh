# Java 中的 Instant isBefore()方法，示例

> 原文:[https://www . geesforgeks . org/instant-is before-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-isbefore-method-in-java-with-examples/)

**isBefore()** 方法的**即时类**检查这个即时时间线位置是否在作为参数传递的即时之前。如果该时刻时间线位置在作为参数传递的时刻之前，则该方法将返回 true 或 false。比较是基于瞬间的时间线位置。

**语法:**

```
public boolean isBefore(Instant otherInstant)

```

**参数:**该方法取一个参数 **otherInstant** ，作为比较的另一个时刻。它不应为空。

**返回:**如果该时刻在指定时刻之前，则该方法返回**真**。

**异常:**如果 otherInstant 为空，该方法抛出**空指针异常**。

下面的程序说明了 isBefore()方法:

**程序 1:**

```
// Java program to demonstrate
// Instant.isBefore() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant1
            = Instant.parse("2018-12-30T09:24:54.63Z");

        // create other Instant
        Instant instant2
            = Instant.parse("2018-12-31T01:34:00.63Z");

        // print instances
        System.out.println("Instance 1: " + instant1);
        System.out.println("Instance 2: " + instant2);

        // check if instant1 is after instant2
        // using isAfter()
        boolean value = instant1.isBefore(instant2);

        // print result
        System.out.println("Is Instant1 before Instant2: "
                           + value);
    }
}
```

**输出:**

```
Instance 1: 2018-12-30T09:24:54.630Z
Instance 2: 2018-12-31T01:34:00.630Z
Is Instant1 before Instant2: true

```

**程序二:**

```
// Java program to demonstrate
// Instant.isBefore() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant1
            = Instant.parse("2018-11-27T09:24:54.63Z");

        // create other Instant
        Instant instant2 = Instant.now();

        // print instances
        System.out.println("Instance 1: " + instant1);
        System.out.println("Instance 2: " + instant2);

        // check if instant1 is after instant2
        // using isAfter()
        boolean value = instant1.isBefore(instant2);

        // print result
        System.out.println("Is Instant1 before Instant2: "
                           + value);
    }
}
```

**输出:**

```
Instance 1: 2018-11-27T09:24:54.630Z
Instance 2: 2018-11-27T04:55:36.127Z
Is Instant1 before Instant2: false

```

**程序 3:** 显示 isBefore 抛出的异常()

```
// Java program to demonstrate
// Instant.isBefore() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant1 = Instant.parse("2018-10-30T19:34:50.63Z");

        // create other Instant
        Instant instant2 = null;

        try {

            // print instances
            System.out.println("Instance 1: " + instant1);
            System.out.println("Instance 2: " + instant2);

            // check if instant1 is after instant2
            // using isAfter()
            boolean value = instant1.isBefore(instant2);
        }
        catch (Exception e) {
            // print result
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Instance 1: 2018-10-30T19:34:50.630Z
Instance 2: null
Exception: java.lang.NullPointerException

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # isb before(Java . time . instant)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#isBefore(java.time.Instant))