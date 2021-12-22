# Java 中的 LocalTime withNano()方法，示例

> 原文:[https://www . geesforgeks . org/local time-with nano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-withnano-method-in-java-with-examples/)

一个 **LocalTime** 类的 **withNano()** 方法用于获取这个 LocalTime 的副本，其中 Nano 被更改为 NaNO，并作为参数传递给这个方法。该本地时间的剩余值将保持不变。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public LocalTime withNano(int nano)

```

**参数:**该方法接受单个参数 **nano** ，表示要在结果中设置的纳米秒，从 0 到 999，999，999。

**返回值:**这个方法返回一个**本地时间实例**基于这个时间与请求的 nano。

**异常:**如果纳米值无效，该方法抛出异常**日期时间异常**

以下程序说明了 withNano()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.withNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // print time
        System.out.println("Old LocalTime: "
                           + time);

        // Get a new LocalDateTime with nanos 100000
        LocalTime newtime = time.withNano(100000);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出:**

```
Old LocalTime: 19:34:50.630
New LocalDateTime: 19:34:50.000100

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.withNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:21:30.13");

        // print time
        System.out.println("Old LocalTime: "
                           + time);

        // Get a new LocalDateTime with nanos 999999
        LocalTime newtime = time.withNano(999999);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出:**

```
Old LocalTime: 01:21:30.130
New LocalDateTime: 01:21:30.000999999

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # with nano(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#withNano(int))