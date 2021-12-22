# Java 中的 LocalTime ofNanoOfDay()方法，示例

> 原文:[https://www . geesforgeks . org/local time-of nano ofday-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-ofnanoofday-method-in-java-with-examples/)

**LocalTime 类**的**of nonofday()**方法用于从一个纳米日值中获取 LocalTime 实例。这将返回一个 LocalTime，指定的纳米是一天，从 0 到 24 * 60 * 60 * 1，000，000，000–1 作为参数传递。

**语法:**

```
public static LocalTime ofNanoOfDay(long nanoOfDay)

```

**参数:**此方法接受单个参数**日纳米**，即日纳米，从 0 到 24 * 60 * 60 * 1，000，000，000–1。

**返回值:**该方法返回**本地时间实例**，该实例是根据作为参数传递的纳米天数创建的。

**异常:**如果作为参数传递的 nanoofDay 值无效，该方法抛出**日期时间异常**。

下面的程序说明了 ofNanoOfDay()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.ofNanoOfDay() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a nano of day
        long nanoofday = 14245000000000l;

        // applying ofNanoOfDay()
        LocalTime value
            = LocalTime.ofNanoOfDay(nanoofday);

        // print result
        System.out.println("LocalTime: "
                           + value);
    }
}
```

**Output:**

```
LocalTime: 03:57:25

```

**程序 2:**

```
// Java program to demonstrate
// LocalTime.ofNanoOfDay() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a nano of day
        long nanoofday = 5000000000l;

        // applying ofNanoOfDay()
        LocalTime value
            = LocalTime.ofNanoOfDay(nanoofday);

        // print result
        System.out.println("LocalTime: "
                           + value);
    }
}
```

**Output:**

```
LocalTime: 00:00:05

```

**参考文献:**