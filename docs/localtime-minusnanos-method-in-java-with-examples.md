# Java 中的 LocalTime minusNanos()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-mins nano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-minusnanos-method-in-java-with-examples/)

**本地时间类**的**亚纳秒()**方法用于从该本地时间中减去指定的纳秒数，并将结果作为本地时间对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```
public LocalTime minusNanos(long nanosecondsToSubtract)

```

**参数:**该方法接受单个参数**纳米秒减去**即需要减去的纳秒值，可以是负值。

**返回值:**该方法返回一个**本地时间**基于该时间减去纳秒。

以下程序说明了纳米粒子()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.minusNanos() method

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

        // subtract 34000000 nanoseconds using minusNanos()
        LocalTime value = time.minusNanos(34000000);

        // print result
        System.out.println("LocalTime after subtraction: "
                           + value);
    }
}
```

**输出:**

```
LocalTime before subtraction: 19:34:50.630
LocalTime after subtraction: 19:34:50.596

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.minusNanos() method

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

        // subtract 971200000 nanoseconds  using minusNanos()
        LocalTime value = time.minusNanos(971200000);

        // print result
        System.out.println("LocalTime after subtraction: "
                           + value);
    }
}
```

**输出:**

```
LocalTime before subtraction: 01:00:01
LocalTime after subtraction: 01:00:00.028800

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # mins nanos(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#minusNanos(long))