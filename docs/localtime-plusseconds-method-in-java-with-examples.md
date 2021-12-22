# Java 中的 LocalTime plusSeconds()方法，示例

> 原文:[https://www . geesforgeks . org/local time-plus seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-plusseconds-method-in-java-with-examples/)

**LocalTime 类**的 **plusSeconds()** 方法用于向该 LocalTime 添加指定的秒数值，并将结果作为 LocalTime 对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```java
public LocalTime plusSeconds(long SecondsToAdd)

```

**参数:**此方法接受单个参数**秒添加**，即要添加的秒值，可以是负值。

**返回值:**该方法返回一个基于该时间的**本地时间**，并加上秒数。

下面的程序说明了 plusSeconds()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.plusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // print LocalTime
        System.out.println("LocalTime before addition: "
                           + time);

        // add 200 Seconds using plusSeconds()
        LocalTime value = time.plusSeconds(200);

        // print result
        System.out.println("LocalTime after addition: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before addition: 19:34:50.630
LocalTime after addition: 19:38:10.630

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.plusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:00:01");

        // print LocalTime
        System.out.println("LocalTime before addition: "
                           + time);

        // add -3400 Seconds using plusSeconds()
        LocalTime value = time.plusSeconds(-3400);

        // print result
        System.out.println("LocalTime after addition: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before addition: 01:00:01
LocalTime after addition: 00:03:21

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # plus seconds(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#plusSeconds(long))