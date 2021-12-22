# Java 中的 LocalTime withSecond()方法，示例

> 原文:[https://www . geesforgeks . org/local time-with second-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-withsecond-method-in-java-with-examples/)

一个 **LocalTime** 类的 **withSecond()** 方法被用来获取这个 LocalTime 的一个副本，其中秒被更改为作为参数传递给这个方法的秒。该本地时间的剩余值将保持不变。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public LocalTime withSecond(int second)

```

**参数:**该方法接受单个参数**秒**，表示在结果中设置的分钟秒，从 0 到 59。

**返回值:**该方法返回一个**本地时间实例**，基于该时间，请求秒。

**异常:**如果第二个值无效，该方法抛出异常**日期时间异常**

下面的程序说明了 withSecond()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.withSecond() method

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

        // Get a new LocalDateTime with seconds 4
        LocalTime newtime = time.withSecond(4);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出:**

```java
Old LocalTime: 19:34:50.630
New LocalDateTime: 19:34:04.630

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.withSecond() method

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

        // Get a new LocalDateTime with seconds 23
        LocalTime newtime = time.withSecond(23);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出:**

```java
Old LocalTime: 01:21:30.130
New LocalDateTime: 01:21:23.130

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # with second(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#withSecond(int))