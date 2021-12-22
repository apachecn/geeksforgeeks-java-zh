# Java 中的 Instant isAfter()方法，示例

> 原文:[https://www . geesforgeks . org/instant-is after-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-isafter-method-in-java-with-examples/)

**isAfter()** 一个**瞬间类**的方法用来检查这个瞬间是否在作为参数传递的瞬间之后。此方法返回一个显示相同内容的布尔值。

**语法:**

```
public boolean isAfter(Instant otherInstant)

```

**参数:**该方法取一个参数 **otherInstant** ，即与该瞬间比较的另一个瞬间。它不应为空。

**返回:**如果这个瞬间在指定的瞬间之后，这个方法返回**真**。否则返回假。

**异常:**如果作为参数传递的 otherInstant 为空，则该方法抛出**空指针异常**。

下面的程序说明了 isAfter()方法:

**程序 1:**

```
// Java program to demonstrate
// Instant.isAfter() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant1
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // create other Instant
        Instant instant2
            = Instant.parse("2018-12-29T09:24:00.63Z");

        // print instances
        System.out.println("Instance 1: " + instant1);
        System.out.println("Instance 2: " + instant2);

        // check if instant1 is after instant2
        // using isAfter()
        boolean value = instant1.isAfter(instant2);

        // print result
        System.out.println("Is Instant1 after Instant2: "
                           + value);
    }
}
```

**输出:**

```
Instance 1: 2018-12-30T19:34:50.630Z
Instance 2: 2018-12-29T09:24:00.630Z
Is Instant1 after Instant2: true

```

**程序二:**

```
// Java program to demonstrate
// Instant.isAfter() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant1
            = Instant.parse("2018-10-30T19:34:50.63Z");

        // create other Instant
        Instant instant2 = Instant.now();

        // print instances
        System.out.println("Instance 1: " + instant1);
        System.out.println("Instance 2: " + instant2);

        // check if instant1 is after instant2
        // using isAfter()
        boolean value = instant1.isAfter(instant2);

        // print result
        System.out.println("Is Instant1 after Instant2: "
                           + value);
    }
}
```

**输出:**

```
Instance 1: 2018-10-30T19:34:50.630Z
Instance 2: 2018-11-27T04:52:08.970Z
Is Instant1 after Instant2: false

```

**程序 3:** 显示 isAfter 抛出的异常()

```
// Java program to demonstrate
// Instant.isAfter() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant1
            = Instant.parse("2018-10-30T19:34:50.63Z");

        // create other Instant
        Instant instant2 = null;

        try {

            // print instances
            System.out.println("Instance 1: " + instant1);
            System.out.println("Instance 2: " + instant2);

            // check if instant1 is after instant2
            // using isAfter()
            boolean value = instant1.isAfter(instant2);
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

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # isaafter(Java . time . instant)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#isAfter(java.time.Instant))