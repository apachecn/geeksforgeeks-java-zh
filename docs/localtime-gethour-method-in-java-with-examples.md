# Java 中的 LocalTime getHour()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-gethour-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-gethour-method-in-java-with-examples/)

**本地时间类**的 **getHour()** 方法用于返回一天中的小时字段。此方法返回一个 0 到 23 之间的整数值，即一天中的小时数。

**语法:**

```java
public int getHour()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个**整数值**，代表一天中的某个时间，范围从 0 到 23。

下面的程序说明了 getHour()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.getHour() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // get Hour field using getHour()
        int Hour = time.getHour();

        // print result
        System.out.println("Hour Field: "
                           + Hour);
    }
}
```

**输出:**

```java
Hour Field: 19

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.getHour() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("23:14:30.53");

        // get Hour field using getHour()
        int Hour = time.getHour();

        // print result
        System.out.println("Hour Field: "
                           + Hour);
    }
}
```

**输出:**

```java
Hour Field: 23

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # getHour()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#getHour())