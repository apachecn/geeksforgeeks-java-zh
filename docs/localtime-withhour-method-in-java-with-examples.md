# Java 中的 LocalTime withHour()方法，示例

> 原文:[https://www . geeksforgeeks . org/local time-with our-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-withhour-method-in-java-with-examples/)

一个 **LocalTime** 类的**withour()**方法用于获取这个 LocalTime 的一个副本，其中将小时数更改为作为参数传递给这个方法的小时数。该本地时间的剩余值将保持不变。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public LocalTime withHour(int hour)

```

**参数:**该方法接受单个参数**小时**，表示在结果中设置的一天中的小时，从 0 到 23。

**返回值:**该方法返回一个**本地时间实例**，基于该时间和请求的小时。

**异常:**如果小时值无效，该方法抛出异常**日期时间异常**

下面的程序说明了 withHour()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.withHour() method

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

        // Get a new LocalDateTime with hours 4
        LocalTime newtime = time.withHour(4);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出:**

```
Old LocalTime: 19:34:50.630
New LocalDateTime: 04:34:50.630

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.withHour() method

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

        // Get a new LocalDateTime with hours 23
        LocalTime newtime = time.withHour(23);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出:**

```
Old LocalTime: 01:21:30.130
New LocalDateTime: 23:21:30.130

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # withour(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#withHour(int))