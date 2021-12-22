# Java 中的 LocalTime minusSeconds()方法，示例

> 原文:[https://www . geesforgeks . org/local time-mins seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-minusseconds-method-in-java-with-examples/)

**LocalTime 类**的 **minusSeconds()** 方法用于从该 LocalTime 中减去指定的秒数值，并将结果作为 LocalTime 对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```java
public LocalTime minusSeconds(long SecondsToSubtract)

```

**参数:**该方法接受单个参数**秒减**，即要减的秒的值，可以是负值。

**返回值:**该方法返回一个基于该时间的**本地时间**，减去秒数。

下面的程序说明了负秒()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.minusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // print LocalTime
        System.out.println("LocalTime before subtraction: "
                           + time);

        // subtract 200 Seconds using minusSeconds()
        LocalTime value = time.minusSeconds(200);

        // print result
        System.out.println("LocalTime after subtraction: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before subtraction: 19:34:50.630
LocalTime after subtraction: 19:31:30.630

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.minusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:00:01");

        // print LocalTime
        System.out.println("LocalTime before subtraction: "
                           + time);

        // subtract -3400 Seconds using minusSeconds()
        LocalTime value = time.minusSeconds(-3400);

        // print result
        System.out.println("LocalTime after subtraction: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before subtraction: 01:00:01
LocalTime after subtraction: 01:56:41

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # mins seconds(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#minusSeconds(long))