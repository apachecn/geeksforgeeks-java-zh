# Java 中的 LocalTime getMinute()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-getminute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-getminute-method-in-java-with-examples/)

**本地时间类**的 **getMinute()** 方法用于返回小时分钟字段。此方法返回一个 0 到 59 之间的整数值，即一小时的分钟数。

**语法:**

```
public int getMinute()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个**整数值**，代表一小时中的分钟，范围从 0 到 59。

下面的程序说明了 getMinute()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.getMinute() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // get Minute field using getMinute()
        int Minute = time.getMinute();

        // print result
        System.out.println("Minute Field: "
                           + Minute);
    }
}
```

**Output:**

```
Minute Field: 34

```

**程序 2:**

```
// Java program to demonstrate
// LocalTime.getMinute() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("23:14:30.53");

        // get Minute field using getMinute()
        int Minute = time.getMinute();

        // print result
        System.out.println("Minute Field: "
                           + Minute);
    }
}
```

**Output:**

```
Minute Field: 14

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # getMinute()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#getMinute())