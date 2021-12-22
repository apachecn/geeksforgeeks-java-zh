# Java 中的 LocalTime withMinute()方法，示例

> 原文:[https://www . geesforgeks . org/local time-with minute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-withminute-method-in-java-with-examples/)

一个 **LocalTime** 类的 **withMinute()** 方法用于获取这个 LocalTime 的一个副本，其中分钟被更改为作为参数传递给这个方法的分钟。该本地时间的剩余值将保持不变。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public LocalTime withMinute(int minute)

```

**参数:**该方法接受单个参数**分钟**，该参数表示要在结果中设置的小时分钟，从 0 到 59。

**返回值:**该方法返回一个**本地时间实例**，基于该时间和请求的分钟数。

**异常:**如果分钟值无效，该方法抛出异常**日期时间异常**

下面的程序说明了 withMinute()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.withMinute() method

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

        // Get a new LocalDateTime with minutes 4
        LocalTime newtime = time.withMinute(4);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出:**

```java
Old LocalTime: 19:34:50.630
New LocalDateTime: 19:04:50.630

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.withMinute() method

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

        // Get a new LocalDateTime with minutes 23
        LocalTime newtime = time.withMinute(23);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出:**

```java
Old LocalTime: 01:21:30.130
New LocalDateTime: 01:23:30.130

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # with minute(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#withMinute(int))