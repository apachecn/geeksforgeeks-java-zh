# Java 中的 LocalTime toNanoOfDay()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-tonanofday-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-tonanoofday-method-in-java-with-examples/)

**LocalTime 类**的 **toNanoOfDay()** 方法用于从这个 LocalTime 返回时间为一天的纳米。此方法返回的值介于 0 到 24 * 60 * 60 * 1，000，000，000–1 之间。

**语法:**

```
public long toNanoOfDay()

```

**参数:**该方法不接受参数。

**返回值:**这个方法返回一个**长值**，是日值的纳米，相当于这个时间。

以下程序说明了 toNanoOfDay()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.toNanoOfDay() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // extract nano of day from toNanoOfDay()
        long value = time.toNanoOfDay();

        // print result
        System.out.println("Nano of day: "
                           + value);
    }
}
```

**输出:**

```
Nano of day: 70490630000000

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.toNanoOfDay() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("23:21:45.98");

        // extract nano of day from toNanoOfDay()
        long value = time.toNanoOfDay();

        // print result
        System.out.println("Nano of day: "
                           + value);
    }
}
```

**输出:**

```
Nano of day: 84105980000000

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # tonanofday()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#toNanoOfDay())