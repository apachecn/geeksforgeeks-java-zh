# Java 中的 LocalTime ofInstant()方法，示例

> 原文:[https://www . geesforgeks . org/local time-of instant-in-Java-method-with-examples/](https://www.geeksforgeeks.org/localtime-ofinstant-method-in-java-with-examples/)

**本地时间类**的 Instant() 方法**用于从作为参数传递的 Instant 和区域 ID 中获取本地时间的实例。在这种方法中，首先，从世界协调时/格林威治时间的偏移是使用区域标识和瞬间获得的。然后，从瞬间和偏移计算出当地时间。**

**语法:**

```
public static LocalTime 
       ofInstant(Instant instant, ZoneId zone)

```

**参数:**此方法接受两个参数:

*   **Moment** : It is the moment when the LocalTime object is created. It should not be empty.
*   **Area** : It is an area with a specified time. It should not be empty.

**返回值:**该方法返回从传递的瞬间创建的**本地时间对象**。

下面的程序说明了 ofInstant()方法:

**节目 1:**

```
// Java program to demonstrate
// LocalTime.ofInstant() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an Instant object
        Instant instant
            = Instant.parse("2018-12-17T19:59:44.770Z");

        // print Instant
        System.out.println("Instant: " + instant);

        // create ZoneId
        ZoneId zoneid = ZoneId.systemDefault();

        // print ZoneId
        System.out.println("ZoneId: " + zoneid);

        // apply ofInstant()
        LocalTime value
            = LocalTime.ofInstant(instant, zoneid);

        // print result
        System.out.println("Generated LocalTime: "
                           + value);
    }
}
```

**输出:**

```
Instant: 2018-12-17T19:59:44.770Z
ZoneId: Etc/UTC
Generated LocalTime: 19:59:44.770

```

**节目 2:**

```
// Java program to demonstrate
// LocalTime.ofInstant() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an Instant object
        Instant instant
            = Instant.parse("2016-11-11T09:19:22Z");

        // print Instant
        System.out.println("Instant: " + instant);

        // apply ofInstant()
        LocalTime value
            = LocalTime.ofInstant(instant,
                                  ZoneId.of("Asia/Dhaka"));

        // print result
        System.out.println("Generated LocalTime: "
                           + value);
    }
}
```

**输出:**

```
Instant: 2016-11-11T09:19:22Z
Generated LocalTime: 15:19:22

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # of instant(Java . time . instant，java.time.ZoneId)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#ofInstant(java.time.Instant, java.time.ZoneId))