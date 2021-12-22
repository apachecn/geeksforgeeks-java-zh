# Java 中的 LocalTime plusNanos()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-plusnanos-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-plusnanos-method-in-java-with-examples/)

**LocalTime 类**的 **plusNanos()** 方法，用于将指定数量的纳秒值添加到该 LocalTime，并将结果作为 LocalTime 对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```java
public LocalTime plusNanos(long nanosecondsToAdd)

```

**参数:**该方法接受单个参数**nanossecond 添加**，即需要添加的纳秒值，可以是负值。

**返回值:**这个方法返回一个基于这个时间加上纳秒的**本地时间**。

下面的程序说明了 plusNanos()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.plusNanos() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // print LocalTime
        System.out.println("LocalTime before add: "
                           + time);

        // add 34000000 nanoseconds using plusNanos()
        LocalTime value = time.plusNanos(34000000);

        // print result
        System.out.println("LocalTime after add: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before add: 19:34:50.630
LocalTime after add: 19:34:50.664

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.plusNanos() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:00:01");

        // print LocalTime
        System.out.println("LocalTime before add: "
                           + time);

        // add -971200000 nanoseconds  using plusNanos()
        LocalTime value = time.plusNanos(-971200000);

        // print result
        System.out.println("LocalTime after add: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before add: 01:00:01
LocalTime after add: 01:00:00.028800

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # plusNanos(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#plusNanos(long))