# Java 中的 LocalTime isBefore()方法，示例

> 原文:[https://www . geesforgeks . org/local time-is before-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-isbefore-method-in-java-with-examples/)

**LocalTime 类**的 **isBefore()** 方法用于检查该 LocalTime 时间轴位置是否在作为参数传递的 LocalTime 之前。如果该 LocalTime 时间线位置在作为参数传递的 LocalTime 之前，则该方法将返回 true 或 false。比较是基于瞬间的时间线位置。

**语法:**

```
public boolean isBefore(LocalTime other)

```

**参数:**该方法接受一个单独的参数 other，即**其他 LocalTime** 对象进行比较。它不应为空。

**返回值:**如果该时间在指定时间之前，则该方法返回 true，否则返回 false。

下面的程序说明了 isBefore()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.isBefore() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time1
            = LocalTime.parse("19:34:50.63");

        // create other LocalTime
        LocalTime time2
            = LocalTime.parse("23:14:00.63");

        // print instances
        System.out.println("LocalTime 1: " + time1);
        System.out.println("LocalTime 2: " + time2);

        // check if LocalTime is before LocalTime
        // using isBefore()
        boolean value = time1.isBefore(time2);

        // print result
        System.out.println("Is LocalTime1 before LocalTime2: "
                           + value);
    }
}
```

**输出:**

```
LocalTime 1: 19:34:50.630
LocalTime 2: 23:14:00.630
Is LocalTime1 before LocalTime2: true

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.isBefore() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time1
            = LocalTime.parse("23:59:11.98");

        // create other LocalTime
        LocalTime time2
            = LocalTime.parse("10:24:53.21");

        // print instances
        System.out.println("LocalTime 1: " + time1);
        System.out.println("LocalTime 2: " + time2);

        // check if LocalTime is before LocalTime
        // using isBefore()
        boolean value = time1.isBefore(time2);

        // print result
        System.out.println("Is LocalTime1 before LocalTime2: "
                           + value);
    }
}
```

**输出:**

```
LocalTime 1: 23:59:11.980
LocalTime 2: 10:24:53.210
Is LocalTime1 before LocalTime2: false

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # is before(Java . time . local time)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#isBefore(java.time.LocalTime))