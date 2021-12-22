# Java 中的 LocalDateTime getSecond()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-get second-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-getsecond-method-in-java-with-examples/)

**本地日期时间类**的 **getSecond()** 方法用于返回分钟秒字段。此方法返回一个从 0 到 59 的整数值，即一分钟的秒数。

**语法:**

```
public int getSecond()

```

**参数:**此方法不接受任何参数。

**返回:**该方法返回一个**整数值**，代表分钟的秒数，范围从 0 到 59。

下面的程序说明了 LocalDateTime.getSecond()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.getSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-03T12:39:10");

        // get SecondOfMinute
        int secondOfMinute = local.getSecond();

        // print result
        System.out.println("SecondOfMinute: "
                           + secondOfMinute);
    }
}
```

**输出:**

```
SecondOfMinute: 10

```

**程序二:**

```
// Java program to demonstrate
// LocalDateTime.getSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2019-01-28T22:29:59");

        // get SecondOfMinute
        int secondOfMinute = local.getSecond();

        // print result
        System.out.println("SecondOfMinute: "
                           + secondOfMinute);
    }
}
```

**输出:**

```
SecondOfMinute: 59

```

参考:t0[https://docs . Oracle . com/javae/9/docs/API/Java/time/localdatetime . html # getsecond]-t1]