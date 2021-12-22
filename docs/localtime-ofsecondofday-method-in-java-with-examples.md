# Java 中的 LocalTime ofSecondOfDay()方法，示例

> 原文:[https://www . geesforgeks . org/local time-of secondofday-in-Java-method-with-examples/](https://www.geeksforgeeks.org/localtime-ofsecondofday-method-in-java-with-examples/)

**LocalTime 类**的 **ofSecondOfDay()** 方法用于从一天中的第二个值获取 LocalTime 实例。这将返回一个本地时间，指定的第二天，从 0 到 24 * 60 * 60–1 作为参数传递。

**语法:**

```
public static LocalTime ofSecondOfDay(long secondOfDay)

```

**参数:**此方法接受单个参数**第二天**，即第二天，从 0 到 24 * 60 * 60–1。

**返回值:**该方法返回从指定的第二天创建的**本地时间实例**。

**异常:**如果第二天的值无效，该方法抛出**日期时间异常**。

下面的程序说明了 ofSecondOfDay()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.ofSecondOfDay() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a nano of day
        long secondvalue = 14245l;

        // applying ofSecondOfDay()
        LocalTime value
            = LocalTime.ofSecondOfDay(secondvalue);

        // print result
        System.out.println("LocalTime: "
                           + value);
    }
}
```

**输出:**

```
LocalTime: 03:57:25

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.ofSecondOfDay() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a nano of day
        long second = 24005;

        // applying ofSecondOfDay()
        LocalTime value
            = LocalTime.ofSecondOfDay(second);

        // print result
        System.out.println("LocalTime: "
                           + value);
    }
}
```

**输出:**

```
LocalTime: 06:40:05

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # of secondofday(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#ofSecondOfDay(long))