# Java 中的 LocalTime minusHours()方法，示例

> 原文:[https://www . geesforgeks . org/local time-minoshours-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-minushours-method-in-java-with-examples/)

**LocalTime 类**的 **minusHours()** 方法用于从该 LocalTime 中减去指定的小时数值，并将结果作为 LocalTime 对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```java
public LocalTime minusHours(long hoursToSubtract)

```

**参数:**该方法接受单个参数**小时减去**，即需要减去的小时数，可以是负值。

**返回值:**该方法根据该时间减去小时数返回一个**本地时间**。

下面的程序说明了 minusHours()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.minusHours() method

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

        // subtract 3 hours using minusHours()
        LocalTime value = time.minusHours(3);

        // print result
        System.out.println("LocalTime after subtraction: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before subtraction: 19:34:50.630
LocalTime after subtraction: 16:34:50.630

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.minusHours() method

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

        // subtract 7 hours using minusHours()
        LocalTime value = time.minusHours(7);

        // print result
        System.out.println("LocalTime after subtraction: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before subtraction: 01:00:01
LocalTime after subtraction: 18:00:01

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # minoshours(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#minusHours(long))