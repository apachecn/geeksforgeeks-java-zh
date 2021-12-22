# Java 中的 LocalTime getSecond()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-get second-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-getsecond-method-in-java-with-examples/)

**本地时间类**的 **getSecond()** 方法用于返回分钟秒字段。此方法返回一个从 0 到 59 的整数值，即一分钟的秒数。

**语法:**

```java
public int getSecond()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个**整数值**，代表分钟的秒数，范围从 0 到 59。

下面的程序说明了 getSecond()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.getSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // get Second field using getSecond()
        int Second = time.getSecond();

        // print result
        System.out.println("Second Field: "
                           + Second);
    }
}
```

**输出:**

```java
Second Field: 50

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.getSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("23:14:30.53");

        // get Second field using getSecond()
        int Second = time.getSecond();

        // print result
        System.out.println("Second Field: "
                           + Second);
    }
}
```

**输出:**

```java
Second Field: 30

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/local time . html # getsecond()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#getSecond())